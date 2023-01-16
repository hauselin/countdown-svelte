<script>
  import moment from "moment";

  let today = moment();
  let start = moment("1989-12-21");
  let end = start.clone().add(55, "y");
  let nextYear = moment().startOf("year").add(1, "year");

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
  <button>{today.diff(start, "days")}</button>
  <button>
    {nextSunday.diff(today, "days")}
  </button>
  <button>
    {nextYear.diff(today, "days")}
  </button>
  <button>
    {end.diff(today, "days")}
  </button>
</main>
