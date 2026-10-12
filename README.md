# TaskFlow (React Native + REST API)

## Запуск
```
npm install
npx expo install --fix   # вирівняти версії під вашу SDK
npx expo start
```
Скануйте QR-код в Expo Go.

## Як працює видалення
1. Кнопка «Видалити» -> `Alert` з підтвердженням.
2. `remove(id)` в `useTasks`: задача одразу зникає зі списку (оптимістичне оновлення).
3. Йде `DELETE /todos/:id` (`src/api/tasks.js`).
4. Якщо запит впав — задача повертається на те саме місце й показується помилка.

Примітка: JSONPlaceholder не зберігає зміни, тож після pull-to-refresh задачі з'являться знову.
Для свого бекенду змініть `BASE_URL` в `src/api/tasks.js`.
