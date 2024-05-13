Methods:

Жизненный цикл (классового) компонента включает в себя 4 фазы

1. Инициализация - Initialization
На данной фазе компонент начинает свой путь, он рождается. И он устанавливает состояние - state. И у него устанавливаются - props. И обычно это делается в методе - constructor.     
state/props - constructor

2. Монтирование - Mounting
На этом этапе компонент монтируется или попадает в DOM. (Виртуальный DOM react).
Загрузка реального DOM занимает много ресурсов, но в react есть виртуальный DOM, который делает так, что все обновляется быстрее. 
Монтирование начинается после завершения стадии Инициализации.   
На этой стадии Render()!!! вызывается первый раз, т.е. наш компонент рендерится или показывается на экране впервый раз.    

componentWillMount()      - Устарел в версии 18.
componentDidMount() +++   Вызывается только 1 раз.

3. Обновление - Updating
Каждый раз, когда меняется состояние компонента происходит повторный рендеринг, те Render() - так же может происходить много раз. 
Изменение состояния и повторный рендеринг.

shouldComponentUpdate()
componentWillUpdate()      - Устарел в версии 18.
componentDidUpdate()

4. Размонтирование - Unmounting
Стадия размонтирования или смерти компонента. Это самый последний этап жизни компонента, он отключается от DOM или он убирается из DOM. 

componentWillUnMount() +++

- И на этом заканчивается жизненный цикл наших компонентов. 



* componentDidMount() 
If you define the componentDidMount method, React will call it when your component is added (mounted) to the screen. This is a common place to start data fetching, set up subscriptions, or manipulate the DOM nodes.

If you implement componentDidMount, you usually need to implement other lifecycle methods to avoid bugs. For example, if componentDidMount reads some state or props, you also have to implement componentDidUpdate to handle their changes, and componentWillUnmount to clean up whatever componentDidMount was doing.