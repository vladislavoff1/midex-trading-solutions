---
description: >-
  Для эффективной работы системы управления ликвидностью необходимо сразу
  несколько роботов, работающий параллельно и взаимодействующими не только с
  пользователями, но и друг с другом
---

# Типы роботов

## **Робот объема или наполнения стаканов**

Стаканы на бирже должны быть наполнены реальными ордерами, иначе пользователь не сможет купить большой объем валюты.

Выставлять ордера больших объемов по близким к рыночным ценам — опасно. Цена может быстро измениться и робот потеряет деньги.

Поэтому робот делит на части весь выделенный для постановки в стакан объем валюты и расставляет ордера на разном расстоянии от рыночной цены. Он устроен так, что чем дальше цена от рыночной, тем больший объем по этой цене выставлен. Самая близкая и самая далекая цена от рыночной настраиваются.

Робот постоянно следит за изменением рыночной цены и переставляет ордера, которые становятся недостаточно безопасными \(выгодными\) для робота.

Для поддержания интереса пользователей робот иногда переставляет свои ордера даже если курс меняется не сильно. Так стакан кажется более «живым» и торговать на валютной паре становится интереснее.

При изменении выделенного на торги ликвидности робот плавно меняет объем стакана, имитируя действия людей, а не роботов.

## **Робот торгов**

Робот ставит две сделки одинакового объема, на продажу и на покупку, по текущему курсу. После отменяет открытые ордера, если они остались. Так робот скупает у пользователей валюту по рыночной или лучшей цене, или, если таких ордеров нет, скупает валюту сам у себя. Это позволяет генерировать на бирже сделки и создает на бирже активность.

Если такого робота не будет, то графики на бирже покажут низкую активность и новые пользователи не будут на бирже торговать.

## **Робот поддержания интереса пользователей**

Робот ставит ордера в стакан по менее выгодным для себя курсам, чем робот объема. Через некоторое время робот их отменяет. Это поддерживает активность в спреде стакана и повышает заинтересованность пользователей в торговле. Робот торгует маленьким объемом, частота сделок регулируется, это позволяет прогнозировать расходы на этого робота.  

