<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Expandable Section</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        details {
            margin-top: 10px;
            border-left: 4px solid #2979ff;
            background-color: #f9f9f9;
            border-radius: 5px;
            transition: all 0.3s ease-in-out;
            box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        details[open] {
            background-color: #ffffff;
        }

        summary {
            font-size: 1.2em;
            font-weight: bold;
            cursor: pointer;
            padding: 10px;
            display: flex;
            align-items: center;
            background-color: #f1f1f1;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        summary:hover {
            background-color: #e0e0e0;
        }

        details p,
        details ul {
            padding: 0 15px;
            margin-bottom: 10px;
        }

        details ul {
            padding-left: 30px;
        }

        details li {
            margin-bottom: 5px;
        }
    </style>
</head>
<body>

    <details>
        <summary>Key Parameters Affecting Projectile Motion</summary>
        <p>Several parameters influence the behavior of a projectile:</p>
        <ul>
            <li><strong>Initial velocity (v₀):</strong> Determines the overall motion, affecting both range and maximum height.</li>
            <li><strong>Angle of projection (θ):</strong> The launch angle plays a crucial role in optimizing the range and trajectory shape.</li>
            <li><strong>Gravitational acceleration (g):</strong> The constant acceleration due to gravity affects the motion, typically taken as 9.81 m/s² on Earth.</li>
            <li><strong>Launch height (h):</strong> If the projectile is launched from a height, it alters the flight time and final landing position.</li>
            <li><strong>Air resistance (optional consideration):</strong> In real-world scenarios, drag affects the motion but is often neglected in basic models.</li>
        </ul>
        <p>By analyzing how these parameters interact, we can develop accurate models to describe and predict projectile trajectories in different conditions.</p>
    </details>

</body>
</html>
