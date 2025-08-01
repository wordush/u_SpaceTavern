#GameManager
Веха: [[Создание скелета игры]]
Тип: Техническая
Сложность: 1
Статус: -
Исполнитель(Киллер): 

## Описание
Управление глобальными системами игры (время, сцены, сохранения, общие переменные)
## Что включает

1. **Поля:**
   Время и прогресс
   - `float currentTime` (0 - 24) часы
   - `int currentDay` (1 - 31) день
   - `int currentMonth` (1 - 4) месяц
   - `int currentYear` (1 - 99) год

   Состояние игры
   - `enum GameState { Playing, Paused, Dialog, Menu }` - Для остановки времени
   - `GameState currentGameState` - текущее состояние игры. Контролирует, что можно делать в текущем состоянии (движение, UI и т.п.)

   Системы и менеджеры
   - `InventoryManager inv_Manager`
   - `UIManager ui_Manager`
   - `SoundManager sound_Manager`
   - `SaveSystem save_System`
   Как работает?
        Все системы и менеджеры должны загружаться в `Awake()`.

   Глобальные переменные
   - `int money`
   - `bool hasSeenIntro`
   - `Dictionary<string, bool> unlockedMachines`
   - `Dictionary<string, bool> unlockedRecipes`
   Как работает?
	   То, что нужно знать игре вне зависимости от локации или конкретной сцены
1. 