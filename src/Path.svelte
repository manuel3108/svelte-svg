<path d={path} stroke={stroke} fill={fill}></path>

<script>
    export let path = undefined
    export let stroke = 'black'
    export let fill = 'transparent'
    export let points = undefined

    $: {
        if (points !== undefined && points.length > 0) {
            let temp = `M${points[0].x} ${points[0].y} `
            for (let i = 0; i < points.length; i++) {
                temp += `L${points[i].x} ${points[i].y} `
            }
            path = temp
        }
    }
</script>