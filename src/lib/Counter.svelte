<script>
  let today = new Date();
  let die = new Date(2049, 12, 21); // 60 years from birthday
  let nextYear = new Date(today.getFullYear() + 1, 0, 1);
  let nextSunday = new Date(
    today.getFullYear(),
    today.getMonth(),
    today.getDate() + ((7 - today.getDay()) % 7)
  );

  const days = (date1, date2) => {
    let difference = date1.getTime() - date2.getTime();
    let TotalDays = Math.ceil(difference / (1000 * 3600 * 24));
    return TotalDays;
  };
</script>

<button>
  {days(nextSunday, today)}
</button>

<button>
  {days(nextYear, today)}
</button>

<button>
  {days(die, today)}
</button>
