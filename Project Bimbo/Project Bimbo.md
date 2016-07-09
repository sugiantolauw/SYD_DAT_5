
Numerical and Categorical Features:

1)	Numerical Features/Continuous Variables:

o	Semana: Week number (from Thursday to Wednesday)
o	Venta_uni_hoy: Sales unit this week (integer)
o	Venta_hoy: Sales figures this week (in pesos)
o	Dev_uni_proxima: Units returned next week (integer)
    Units returned are delayed by 1 week. 
    So, either I lag everything by 1 week (and lose 1 week in training) or find a way to incorporate N-1 information in first week
    which isn't provided. This would require forecasting and potential bias in final model.
o	Dev_proxima: Price of returned items (pesos)
o	Demanda_uni_equil: Demand (this is what I’m going to predict)
    The calculation of current demand is defined as sales this week subtracted by the return next week.
    The adjusted demand (Demanda_uni_equil) is always >= 0 since demand should be either 0 or a positive value. 
    The reason that Venta_uni_hoy - Dev_uni_proxima sometimes has negative values is that the returns records sometimes carry over a few weeks

2)	Categorical Features:

o	Semana - Week number (from Thursday to Wednesday)
o	Agencia_ID — Sales Depot ID
o	Town - Town (in different file, town_state.csv)
o	State - State (in different file, town_state.csv)
o	Canal_ID — Sales Channel ID
o	Ruta_SAK — Route ID (Several routes = Sales Depot)
o	Cliente_ID — Client ID 
    There are duplicate Cliente_ID's in cliente_tabla, which means one Cliente_ID may have multiple NombreCliente that are very similar. This is due to the NombreCliente being noisy and not standardized in the raw data.
o	NombreCliente — Client name (in different file, cliente_tabla.csv)
o	Producto_ID — Product ID
o	NombreProducto — Product Name (in different file, producto_tabla.csv)

