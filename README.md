# CHALLENGE: Predicción de Cancelación de Clientes

## Descripción del Proyecto

Este proyecto realiza un **análisis predictivo** para identificar clientes en riesgo de cancelación (churn) en una empresa.  
Se utilizan dos modelos predictivos principales: **Random Forest** y **Regresión Logística**.

---

## 📂 Desarrollo

1. **Carga de Datos:**  
   Se utilizaron los datos tratados en el reto 1, ya depurados y listos para análisis.

2. **Codificación One-Hot:**  
   - Se aplicó **One-Hot Encoding** para transformar las variables categóricas en formato numérico, compatible con los modelos.  
   - Antes de esto, se modificaron las variables de tipo `object` asignando `1` para "Sí" y `0` para "No".  
   - Se eliminaron las variables `No-Phone-Service` y `No-Internet-Service`, escalando sus valores a `0` para mantener consistencia.

3. **División de Datos:**  
   - El conjunto de datos se dividió en **entrenamiento** y **prueba** para evaluar correctamente los modelos.

4. **Modelado:**  
   - Se entrenaron los modelos **Random Forest** y **Regresión Logística**.  
   - Se evaluó la **importancia de las variables** y el desempeño de cada modelo utilizando métricas como exactitud, precisión, recall y F1-score.

---

## Conclusiones

1. **Desempeño de los modelos:**  
   - **Random Forest** mostró mejor desempeño general, con exactitud alrededor de 85%, y un balance razonable entre precisión y recall para la clase minoritaria (clientes que cancelan).  
   - **Regresión Logística** es útil para interpretar la influencia de cada variable, aunque su desempeño fue menor (exactitud ~78%).

2. **Factores más importantes que afectan la cancelación:**  
   - **Antigüedad del cliente (Customer_Tenure):** los clientes más nuevos tienen mayor riesgo de cancelar.  
   - **Tipo de contrato (Account_Contract):** contratos a largo plazo reducen la probabilidad de churn.  
   - **Método de pago (Account_PaymentMethod):** pagos electrónicos están asociados a mayor riesgo de cancelación.  
   - **Servicios de Internet y soporte:** la falta de servicios como `Internet_OnlineSecurity` o `Internet_TechSupport` aumenta la probabilidad de churn.  
   - **Gasto total y mensual (Charges_Total, Charges_Monthly):** clientes con menor gasto tienden a cancelar más.

3. **Recomendaciones de negocio:**  
   - Incentivar **contratos de mayor duración** y **servicios adicionales** para clientes nuevos.  
   - Promover **métodos de pago automáticos** que reduzcan la fricción y el riesgo de cancelación.  
   - Monitorear clientes con bajo gasto o nuevos, aplicando **acciones preventivas de retención**.

4. **Importancia del análisis predictivo:**  
   - Este modelo permite priorizar esfuerzos de retención y optimizar recursos, enfocándose en los clientes con mayor riesgo de churn.
