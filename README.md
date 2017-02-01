# Practica1
temporal <- tempfile()
download.file("http://www.beta.inegi.org.mx/contenidos/proyectos/enchogares/regulares/enoe/microdatos/enoe_15ymas/2016/2016trim1_dbf.zip",temporal)
files=unzip(temporal, list=TRUE)$Name
unzip(temporal, files=files[grepl("dbf",files)])
install.packages("foreign")
require(foreign)
SDEMT116 <- data.frame(read.dbf("sdemt116.dbf"))
View (SDEMT116) 
####################################################
nombres <- c("sergio","carlos","paula")
edad <- c(23,43,51)
base1 <- data.frame(nombres,edad)
3+4
table(SDEMT116$SEX)   #tabla para la variable sexo
table(SDEMT116$ENT)  #tabla para la variable entidad
wtd.table (SDEMT116$SEX, SDEMT116$FAC) #ponderar tu base de datos, expandir tu muestra 
install.packages("questionr") #bajar de internet la libreria
require(questionr) #mandamos llamar la libreria a mi sesion de R
