<script>
  let today = new Date();
  let date60 = new Date(2049, 12, 21); // 60 years from birthday
  let nextYear = new Date(today.getFullYear() + 1, 0, 1);
  let nextSunday = new Date(
    today.getFullYear(),
    today.getMonth(),
    today.getDate() + ((7 - today.getDay()) % 7)
  );

  const days = (end, start) => {
    let difference = end.getTime() - start.getTime();
    let diffDays = Math.ceil(difference / (1000 * 3600 * 24));
    return diffDays;
  };

  // https://stackoverflow.com/questions/1643320/get-month-name-from-date
  const month = today.toLocaleString("default", { month: "long" });
</script>

<main>
  <p>{month}, {today.getDate()}</p>
  <button>
    {days(nextSunday, today)}
  </button>

  <button>
    {days(nextYear, today)}
  </button>

  <button>
    {days(date60, today)}
  </button>
</main>
