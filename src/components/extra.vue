
		<select name="inputType" id="inputType">
			<option value="millimeter">millimeter</option>
			<option value="centimeter">Centimeter</option>
			<option value="meter">Meter</option>
			<option value="kilometer">Kilometer</option>
		</select>

		<div type="text" name="converterResult" id="converterResult">
			
		</div>
		<select name="resultType" id="resultType">
			<option value="millimeter">millimeter</option>
			<option value="centimeter">Centimeter</option>
			<option value="meter">Meter</option>
			<option value="kilometer">Kilometer</option>
		</select>


#converterInput, #converterResult, #inputType, #resultType {
	display: flex;
	flex-direction: column;
	justify-content: center;
	background: #fff;
} 

#converterInput, #converterResult {
	width: 80%;
	height: 2rem;
	padding: 1rem;
	margin: 2rem 1.5rem 0 1.5rem;
	border: 0.2rem solid #6f5643;
	border-radius: 0.5rem;
}

#inputType, #resultType {
	width: 80%;
	font-size: 0.7rem;
	height: auto;
	padding: 0.2rem;
	margin: 0.5rem 1.5rem 1rem 1.5rem;
	border-radius: 0.25rem;
	transition: 0.2s;
	cursor: pointer;
}

#inputType:hover, #resultType:hover {
	background-color: rgb(141, 206, 141);