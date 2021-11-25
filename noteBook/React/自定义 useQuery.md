### 自定义 useQuery

```js
import {
  useLocation
} from "react-router-dom”;

function useQuery() {
  return new URLSearchParams(useLocation().search);
}
```

