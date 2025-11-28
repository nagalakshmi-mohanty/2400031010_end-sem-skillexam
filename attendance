import { useReducer } from "react";

const initialState = [
  { id: 1, name: "Aishwarya", status: "Not Marked" },
  { id: 2, name: "Nikki", status: "Not Marked" },
  { id: 3, name: "Lavani", status: "Not Marked" },
];

function reducer(state, action) {
  switch (action.type) {
    case "MARK_PRESENT":
      return state.map((s) =>
        s.id === action.id ? { ...s, status: "Present" } : s
      );
    case "MARK_ABSENT":
      return state.map((s) =>
        s.id === action.id ? { ...s, status: "Absent" } : s
      );
    case "RESET":
      return initialState;
    default:
      return state;
  }
}

export default function App() {
  const [students, dispatch] = useReducer(reducer, initialState);

  return (
    <div style={{ padding: "20px" }}>
      <h2>Student Attendance Tracker</h2>
      <table border="1" cellPadding="10">
        <thead>
          <tr>
            <th>Name</th>
            <th>Status</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody>
          {students.map((s) => (
            <tr key={s.id}>
              <td>{s.name}</td>
              <td>{s.status}</td>
              <td>
                <button onClick={() => dispatch({ type: "MARK_PRESENT", id: s.id })}>
                  Present
                </button>
                <button onClick={() => dispatch({ type: "MARK_ABSENT", id: s.id })}>
                  Absent
                </button>
              </td>
            </tr>
          ))}
        </tbody>
      </table>
      <br />
      <button onClick={() => dispatch({ type: "RESET" })}>Reset All</button>
    </div>
  );
}
