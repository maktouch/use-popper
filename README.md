# Use Popper

![npm](https://img.shields.io/npm/dt/use-popper.svg)
![npm](https://img.shields.io/npm/v/use-popper.svg)
![NpmLicense](https://img.shields.io/npm/l/use-popper.svg)

[![Edit usePopper](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/mzkm04xqw8?fontsize=14)

```js
import React from 'react';
import usePopper from 'use-popper';
import { useHover } from 'use-events';

function useTooltip(props) {
  const { placement, referrence, popper, arrow } = usePopper({ placement: 'bottom' });
  const [active, bind] = useHover();

  return (
    <div>
      <button ref={referrence.ref} {...bind}>
        hover me
      </button>
      {active && (
        <div ref={popper.ref} style={popper.styles} data-placement={placement}>
          <div>Hello!</div>
          <div ref={arrow.ref} style={arrow.styles} />
        </div>
      )}
    </div>
  );
};

export default useTooltip;
```
