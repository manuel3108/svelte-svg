<path d={path} stroke={stroke} fill={fill}></path>

<script>
    export let path
    export let stroke = 'black'
    export let fill
    export let points

    $: {
        if (points !== undefined) {
            let temp = `M${points[0].x} ${points[0].y} `
            for (let i = 0; i < points.length; i++) {
                temp += `L${points[i].x} ${points[i].y} `
            }
            path = temp
        }
    }
</script>