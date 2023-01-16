<script>
  import moment from "moment";

  let today = moment();
  let start = moment("1989-12-21");
  let end = start.clone().add(55, "y");
  let nextYear = moment().startOf("year").add(1, "year");
  let perc = (today.diff(start, "days") / end.diff(start, "days")) * 100;

  const dayRequired = 7;
  let nextSunday;
  if (moment().isoWeekday() <= dayRequired) {
    nextSunday = moment().isoWeekday(dayRequired);
  } else {
    nextSunday = moment().add(1, "weeks").isoWeekday(dayRequired);
  }
</script>

<main>
  <p>
    {today.format("LLLL")}
  </p>
  <p>
    <button>
      {nextSunday.diff(today, "days")}
    </button>
    <button>
      {nextYear.diff(today, "days")}
    </button>
  </p>
  <p>
    <button>{today.diff(start, "days")}</button>
    <button>
      {end.diff(today, "days")}
    </button>
    <button>
      {perc.toFixed(1)}%
    </button>
  </p>
</main>
