# How to run a clean up function on component destroy

If your effect returns a function, React will run it when it is time to clean up:

```javascript
useEffect(() => {
  chart.current = createChart('chart-container', {
    width: 960,
    height: 500,
    crosshair: {
      mode: CrosshairMode.Normal,
    }
  });

  return function () {
    chart.current?.remove();
  }
}, []);
```

References:
* https://reactjs.org/docs/hooks-effect.html