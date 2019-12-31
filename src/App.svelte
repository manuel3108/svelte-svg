<script>
    import SVG from './SVG.svelte'
    import Path from './Path.svelte'
    import Circle from './Circle.svelte'
    import Ellipse from './Ellipse.svelte'
    import Line from './Line.svelte'
    import Rect from './Rect.svelte'

    let paths = []

    let path = {
        path: 'M 10 10 H 90 V 90 H 10 Z',
        stroke: 'red',
        fill: 'transparent',
    }

    paths.push(path)
    paths = paths

    let path2 = {
        stroke: 'red',
        fill: 'transparent',
        points: [
            { x: 100, y: 100 },
            { x: 50, y: 50 },
            { x: 0, y: 50 },
        ],
    }

    paths.push(path2)
    paths = paths

    setTimeout(() => {
        path.path = 'M 50 10 H 90 V 90 H 10 Z';

        path2.points.push({ x: 0, y: 0});

        paths = paths
        console.log("updated")
    }, 1000)
</script>

<SVG>
    {#each paths as { path, stroke, fill, points }}
        <Path path={path} stroke={stroke} fill={fill} points={points} />
    {/each}
    <Circle centerX=50 centerY=50 radius=20 />
    <Ellipse />
    <Line stroke='blue'/>
    <Rect />
</SVG>