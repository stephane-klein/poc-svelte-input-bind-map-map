<script>
    import { range } from 'radash';

    let myMap = new Map([
        [
            2021,
            new Map([
                [1, "a"],
                [2, "b"],
                [3, "c"],
                [4, "d"],
                [5, "e"],
                [6, "e"],
                [7, "e"],
                [8, "e"],
                [9, "e"],
                [10, "e"],
                [11, "e"],
                [12, "e"]
            ])
        ],
        [
            2022,
            new Map([
                [1, "a"],
                [2, "b"],
                [3, "c"],
                [4, "d"],
                [5, "e"],
                [6, "e"],
                [7, "e"],
                [8, "e"],
                [9, "e"],
                [10, "e"],
                [11, "e"],
                [12, "e"]
            ])
       ],
       [
           2023,
           new Map([
                [1, "a"],
                [2, "b"],
                [3, "c"],
                [4, "d"],
                [5, "e"],
                [6, "e"],
                [7, "e"],
                [8, "e"],
                [9, "e"],
                [10, "e"],
                [11, "e"],
                [12, "e"]
           ])
       ]
    ]);

    console.log(myMap);
</script>

<p>Editable table:</p>

<table>
    <tr>
        <th></th>
        {#each Array.from(range(1, 12)) as month}
            <th>{month}</th>
        {/each}
    </tr>
    {#each myMap.entries() as [year, yearMonth]}
        <tr>
            <th>{year}</th>
            {#each yearMonth.entries() as [_, v]}
                <td>
                    <input
                        type="text"
                        bind:value={v}  // <== this problem is here
                        style="width: 4em"
                    />
                </td>
            {/each}
        </tr>
    {/each}
</table>

<p>View Table:</p>

<table>
    <tr>
        <th></th>
        {#each Array.from(range(1, 12)) as month}
            <th>{month}</th>
        {/each}
    </tr>
    {#each myMap.entries() as [year, yearMonth]}
        <tr>
            <th>{year}</th>
            {#each yearMonth.entries() as [_, v]}
                <td>
                    {v}
                </td>
            {/each}
        </tr>
    {/each}
</table>
