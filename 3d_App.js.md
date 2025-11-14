mport { Provider, useSelector, useDispatch } from "react-redux";
import store, { inc, dec } from "./store";

function Counter() {
  const count = useSelector(s => s.value);
  const dispatch = useDispatch();
  return (
    <div>
      <h2>{count}</h2>
      <button onClick={() => dispatch(inc())}>+</button>
      <button onClick={() => dispatch(dec())}>-</button>
    </div>
  );
}

export default function App() {
  return (
    <Provider store={store}>
      <Counter />
    </Provider>
  );
}
