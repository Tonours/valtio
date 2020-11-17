# Valtio

[![Build Status](https://img.shields.io/github/workflow/status/pmndrs/valtio/Lint?style=flat&colorA=000000&colorB=000000)](https://github.com/pmndrs/valtio/actions?query=workflow%3ALint)
[![Build Size](https://img.shields.io/bundlephobia/min/valtio?label=bundle%20size&style=flat&colorA=000000&colorB=000000)](https://bundlephobia.com/result?p=valtio)
[![Version](https://img.shields.io/npm/v/valtio?style=flat&colorA=000000&colorB=000000)](https://www.npmjs.com/package/valtio)
[![Downloads](https://img.shields.io/npm/dt/valtio.svg?style=flat&colorA=000000&colorB=000000)](https://www.npmjs.com/package/valtio)
[![Discord Shield](https://img.shields.io/discord/740090768164651008?style=flat&colorA=000000&colorB=000000&label=discord&logo=discord&logoColor=ffffff)](https://discord.gg/ZZjjNvJ)

## Quick Start

```jsx
import { create, useProxy } from 'valtio'

const globalState = create({ count: 0, text: 'hello' })

setInterval(() => {
  ++globalState.count
}, 1000)

const Counter = () => {
  const snapshot = useProxy(globalState);
  return (
    <div>
      {snapshot.count}
      <button onClick={() => ++globalState.count}>+1</button>
    </div>
  );
};
```