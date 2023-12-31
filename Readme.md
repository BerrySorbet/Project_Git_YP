Из «Бета-Банка» стали уходить клиенты. Каждый месяц. Немного, но заметно. Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.

Нужно спрогнозировать, уйдёт клиент из банка в ближайшее время или нет. Вам предоставлены исторические данные о поведении клиентов и расторжении договоров с банком. 

Постройте модель с предельно большим значением *F1*-меры. Чтобы сдать проект успешно, нужно довести метрику до 0.59. Проверьте *F1*-меру на тестовой выборке самостоятельно.

Дополнительно измеряйте *AUC-ROC*, сравнивайте её значение с *F1*-мерой.


В данном случае наш целевой признак **"Exited" - факт ухода клиента**. Он бинарный (двоичный), значит, это задача классификации, обучение с учителем.

**Признаки:**

1. **CreditScore** — кредитный рейтинг (не соповставим с балансом на счете, так как у человека может быть 30 000 условных единиц на счете с кредитным рейтингом 100. **Требует масштабирования** в последующем);

2. **Geography** — страна проживания (очевидно, **требует обработки OHE в последующем**, так как это категориальный признак);

3. **Gender** — пол (категориальный признак, **требует обработки OHE**);

4. **Age** — возраст (**требует масштабирования** аналогично пункту 1);

5. **Tenure** — сколько лет человек является клиентом банка (**требует масштабирования** аналогично пункту 1);

6. **Balance** — баланс на счёте (**требует масштабирования** аналогично пункту 1);

7. **NumOfProducts** — количество продуктов банка, используемых клиентом (**требует масштабирования** аналогично пункту 1);

8. **HasCrCard** — наличие кредитной карты (необходимо просто проверить, только ли 0 и 1 проставлены в столбце. Если да, то ничего делать не надо);

9. **IsActiveMember** — активность клиента (аналогично пункту 8);

10. **EstimatedSalary** — предполагаемая зарплата (**требует масштабирования** аналогично пункту 1).

Для решения этой задачи были использованы модели дерева решений, ансамбля деревьев, логистическая регресия.