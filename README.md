# chckOne
```Ruby
import React,{useState} from 'react'
import heroImg from "../../assets/Images/Refine/refine2.png"
import {  useNavigate } from 'react-router-dom';
const PayoutT = () => {
    const navigate=useNavigate()
  const [show, setShow] = useState(false);

  const [isExpanded, setIsExpanded] = useState(false);

  const [name, setName] = useState('');
  const [email, setEmail] = useState('');
  const [pin, setPin] = useState('');
  const [pan, setPan] = useState('');
  const [phone, setPhone] = useState('');

  const [nameError, setNameError] = useState('');
  const [emailError, setEmailError] = useState('');
  const [pinError, setPinError] = useState('');
  const [panError, setPanError] = useState('');
  const [phoneError, setPhoneError]= useState('');
  const [selectedError, setSelectedError]= useState('');
  const [selectedOption , setSelectedOption] = useState ('');

  const handleOptionChange = (e) =>{
    setSelectedOption(e.target.value); 
  }

 

const handleSubmit = (e) => {
    e.preventDefault();
    if (validate()) {
      console.log('Form submitted');
      navigate('/')
    } else {
        
      console.log('Form not submitted');
    }
  };
  const handleMouseEnter =() =>{
    setIsExpanded(true);
  }

  const isValidEmail = (email) => {
    var emailRegex =  /^[a-zA-Z0-9_.+-]+@[a-z]+.[a-z]{2,3}$/;
    return emailRegex.test(email);
  };

  const isValidPin = (pin) => {
    var pinRegex = /^[0-9]{6}$/
    return pinRegex.test(pin);
  }

const isValidPan = (pan) =>{
    var panRegex = /^[a-zA-Z]{3}[PCHFATBLJG]{1}[a-zA-Z]{1}[0-9]{4}[a-zA-Z]{1}$/;
    return panRegex.test(pan);
}
const isValidPhone = (phone) =>{
    var phoneRegex = /^[6-9]{1}[0-9]{9}$/
    return phoneRegex.test(phone);
}

  const validate = () =>{
    let emailError = '';
    let pinError = '';
    let panError = '';
    let phoneError = '';
    let nameError = '';
    // let selectedError = '';



    if(!name){
        nameError = 'Please enter your full name'
    }
    if (!email){
        emailError = 'Email is required';
      }else if(!isValidEmail(email)){
        emailError = 'Please enter valid email address'
      }
    if(!pin){
        pinError = 'Pin required';
    }else if(!isValidPin(pin)){
        pinError = 'Please enter correct PIN'
    }
    if(!pan){
        panError = 'PAN required'
    }else if(!isValidPan(pan)){
        panError = 'Please enter correct PAN'
    }
    if(!phone){
        phoneError = 'Phone number required'
    }else if(!isValidPhone(phone)){
        phoneError= 'Please enter correct phone number'
    }
    // if(!selectedOption){
    //     selectedError= 'Please select your Query'
    // }


    setNameError(nameError);
    setEmailError(emailError);
    setPinError(pinError);
    setPanError(panError);
    setPhoneError(phoneError);
    setSelectedError(selectedError)
    if(nameError){
        return false;
    }
      if (emailError) {
        return false;
      }
      if( pinError){
        return false;
      }
      if(panError){
        return false;
      }
      if(phoneError){
        return false;
      }
      if(selectedError){
        return false;
      }
}

 
  
//   const handleMouseLeave=() =>{
//     setIsExpanded(false);
//   }
//   window.scrollTo(0,0)
  return (
      <div className="py-2 bg-gray-100 overflow-y-hidden">
          {/* Code block starts */}
          <dh-component>
            
              <div className="w-full px-6">
                  <div className="mt-8  rounded-lg bg-indigo-700 container mx-auto flex flex-col items-center pt-12 sm:pt-24 pb-24 sm:pb-32 md:pb-48 lg:pb-56 xl:pb-64">
                      <img className="mr-2 lg:mr-12 mt-2 lg:mt-12 absolute right-0 top-0" src="https://tuk-cdn.s3.amazonaws.com/can-uploader/center_aligned_with_image-svg2.svg" alt="bg" />
                      <img className="ml-2 lg:ml-12 mb-2 lg:mb-12 absolute bottom-0 left-0" src="https://tuk-cdn.s3.amazonaws.com/can-uploader/center_aligned_with_image-svg3.svg" alt="bg" />
                      <div className="w-11/12 sm:w-2/3 mb-5 sm:mb-10">
                          <h1 className="text-2xl sm:text-3xl md:text-4xl lg:text-5xl xl:text-6xl text-center text-white font-bold leading-tight">We manage factors that positivity impact your credit.</h1>
                      </div>
                     
                  </div>
                  <div className="container mx-auto flex justify-center md:-mt-56 -mt-20 sm:-mt-40">
                      <div className=" shadow-xl shadow-l-xl rounded-2xl  m-4 sm:w-2/3 w-11/12">
                          <img className='rounded-2xl' src={heroImg} alt="Sample Page" />
                      </div>
                  </div>
              </div>
          </dh-component>
          {/* Code block ends */}


          <div className="w-full flex items-center justify-center my-12">
                <div className=" top-40 bg-gray-200 shadow-lg rounded-2xl py-12 lg:px-28 px-8">
                    <p className="md:text-3xl text-2xl font-semibold leading-7 text-center text-gray-700">Submit Your Query</p>
                    <form onSubmit={handleSubmit}>
                    <div className="grid md:grid-cols-2 items-center mt-12">
                        <div className="md:w-72 flex flex-col md:p-6 p-2">
                            <label className="text-xl font-semibold leading-none text-gray-800" >Name</label>
                            <input tabIndex={0} arial-label="Enter your name" type="name" className="text-base leading-none text-gray-900 p-3 focus:oultine-none focus:border-indigo-700 mt-4 bg-purple-100 border rounded border-gray-200 shadow-lg placeholder-gray-500 rounded-xl" placeholder="Please input  name" onChange={(e) => setName(e.target.value)}/>
                        <div style={{ color: 'red' }}>{nameError}</div>
                        </div>

                        <div className="md:w-72 flex flex-col md:p-6 p-2">
                            <label className="text-xl font-semibold leading-none text-gray-800">Email Address</label>
                            <input tabIndex={0} arial-label="Your email address" type="name" className="text-base leading-none text-gray-900 p-3 focus:oultine-none focus:border-indigo-700 mt-4 bg-purple-100 border rounded border-gray-200 shadow-lg placeholder-gray-500 rounded-xl" placeholder="Please input email address" onChange={(e) => setEmail(e.target.value)}/>
                           
                        <div style={{ color: 'red' }}>{emailError}</div>
                        </div>
                        <div className="md:w-72 flex flex-col md:p-6 p-2">
                            <label className="text-xl font-semibold leading-none text-gray-800">Pin Code</label>
                            <input tabIndex={0} role="input" arial-label="enter your PIN code" type="name" className="text-base leading-none text-gray-900 p-3 focus:oultine-none focus:border-indigo-700 mt-4 bg-purple-200 border shadow-lg rounded border-gray-200 placeholder-gray-500 rounded-xl" placeholder="Please input company name" maxLength={6} onChange={(e) => setPin(e.target.value)}/>
                           
                        <div style={{ color: 'red' }}>{pinError}</div>
                        </div>

                        <div className="md:w-72 flex flex-col md:p-6 p-2">
                            <label className="text-xl font-semibold leading-none text-gray-800">Pan Number</label>
                            <input tabIndex={0} arial-label="Please input country name" type="name" className="text-base leading-none text-gray-900 p-3 focus:oultine-none focus:border-indigo-700 mt-4 bg-purple-200 border rounded border-gray-200 shadow-lg placeholder-gray-500 rounded-xl" placeholder="Please input country name" onChange={(e) => setPan(e.target.value)} />
                        <div style={{ color: 'red' }}>{panError}</div>
                        </div>
                        <div className="md:w-72 flex flex-col md:p-6 p-2">
                            <label className="text-xl font-semibold leading-none text-gray-800">Phone Number</label>
                            <input tabIndex={0} arial-label="Please input country name" type="name" className="text-base leading-none text-gray-900 p-3 focus:oultine-none focus:border-indigo-700 mt-4 bg-purple-200 border rounded border-gray-200 shadow-lg placeholder-gray-500 rounded-xl" placeholder="Please input country name" onChange={(e) => setPhone(e.target.value)}/>
                    <div style={{ color: 'red' }}>{phoneError}</div>
                        </div>
                    </div>
                    <div className='my-8'>
                            <label className="text-xl font-semibold leading-none text-gray-800 ">Your Query</label>
                        <div className="w-full flex flex-col mt-4 bg-pink-200 p-3 rounded-xl shadow-lg">
                           
                            <span className='mb-3'>
                            <input type="checkbox" value="option1" checked={selectedOption === 'option1'} onChange={handleOptionChange} />
                            <label htmlFor="salaried" className='text-base font-semibold mx-3 text-gray-700'>Need fresh loan/CC to clear outstandings?</label>
                        </span>
                        <span className='my-3'>
                            <input type="checkbox" value="option2" checked={selectedOption === 'option2'} onChange={handleOptionChange} />
                            <label htmlFor="salaried" className='text-base font-semibold mx-3 text-gray-700'>Settle the existing loan</label>
                        </span>
                        <span className='my-3'>
                            <input type="checkbox" value="option3" checked={selectedOption === 'option3'} onChange={handleOptionChange} />
                            <label htmlFor="salaried" className='text-base font-semibold mx-3 text-gray-700'>Pay partial payment of existing account and pay in EMIs</label>
                        </span>
                        <span className='my-3'>
                            <input type="checkbox" value="option4" checked={selectedOption === 'option4'} onChange={handleOptionChange} />
                            <label htmlFor="salaried" className='text-base font-semibold mx-3 text-gray-700'>Just want to improve the credit score</label>
                        </span>
                        <span className='my-3'>
                            <input type="checkbox" value="option5" checked={selectedOption === 'option5'} onChange={handleOptionChange} />
                            <label htmlFor="salaried" className='text-base font-semibold mx-3 text-gray-700'>Get rid off the recurring phone calls of recovery</label>
                        </span>
                        <span className='my-3'>
                            <input type="checkbox" value="option6" checked={selectedOption === 'option6'} onChange={handleOptionChange} />
                            <label htmlFor="salaried" className='text-base font-semibold mx-3 text-gray-700'>Close existing account</label>
                        </span>
                        <span className='mt-3'>
                            <input type="checkbox" value="option7" checked={selectedOption === 'option7'} onChange={handleOptionChange} />
                            <label htmlFor="salaried" className='text-base font-semibold mx-3 text-gray-700'>Others</label>
                        </span>
                        </div>
                    <div style={{ color: 'red' }}>{selectedError}</div>

                    </div>

                    {/* <div className='my-8'>
                            <label className="text-xl font-semibold leading-none text-gray-800 ">Your Query</label>


                        <div className="w-full flex flex-col mt-4 bg-pink-200 p-3 rounded-xl shadow-lg">
                           <span className='mb-3'>


                            <input type="checkbox" onChange={handleOptionChange}   value="Need fresh loan/CC to clear outstandings?"  />
                            <label  className='text-base font-semibold mx-3 text-gray-700'>Need fresh loan/CC to clear outstandings?</label>
                        </span>


                        <span className='my-3'>
                            <input type="checkbox"  onChange={handleOptionChange}  value="Settle the existing loan" />
                            <label  className='text-base font-semibold mx-3 text-gray-700'>Settle the existing loan</label>
                        </span>


                        <span className='my-3'>
                            <input type="checkbox"  onChange={handleOptionChange}  value="Pay partial payment of existing account and pay in EMIs" />
                            <label  className='text-base font-semibold mx-3 text-gray-700'>Pay partial payment of existing account and pay in EMIs</label>
                        </span>


                        <span className='my-3'>
                            <input type="checkbox"  onChange={handleOptionChange}  value="Just want to improve the credit score" />
                            <label  className='text-base font-semibold mx-3 text-gray-700'>Just want to improve the credit score</label>
                        </span>


                        <span className='my-3'>
                            <input type="checkbox"  onChange={handleOptionChange}  value="Get rid off the recurring phone calls of recovery"/>
                            <label  className='text-base font-semibold mx-3 text-gray-700'>Get rid off the recurring phone calls of recovery</label>
                        </span>


                        <span className='my-3'>
                            <input type="checkbox"  onChange={handleOptionChange}  value="Close existing account" />
                            <label  className='text-base font-semibold mx-3 text-gray-700'>Close existing account</label>
                        </span>


                        <span className='mt-3'>
                            <input type="checkbox" value="others"   onChange={handleOptionChange} />
                            <label  className='text-base font-semibold mx-3 text-gray-700'>Others</label>
                        </span>


                        </div>
                    </div> */}
                    <p className="text-sm leading-3 text-red-900 mt-8 px-3">By clicking submit you agree to our terms of service & privacy policy.</p>
                    <div className='w-80 text-sm text-gray-900 mt-8 '>
                    <p className= {isExpanded ? 'expand': 'truncate'} onClick={handleMouseEnter} >CreditKlick does not sell any loans on our own and do not charge any fee from any customers/viewers. We advise customers/viewers to choose from best offers from Banks and its advertisers. We do not guarantee any loans as loan sanction is as per Banks and Nbfcs. We suggest all users to never pay any upfront amount for any loan disbursal and if any person who call you as representative of CreditKlick and ask for any amount report the incident immediately via putting us a mail at <a href="mailto:support@creditklick.com" className='text-blue-800'>support@creditklick.com</a></p></div>
                    <div id="button" className={`${show ? "hidden" : "flex"}   my-8 justify-center items-center w-auto`}>
              
                        <button  className="m-auto text-base font-semibold leading-none text-white py-4 px-10 bg-indigo-500 rounded hover:bg-indigo-700  rounded-full">SUBMIT</button>
               
                    </div>
                    </form>
                </div>
            </div>

      </div>

  );

}

export default PayoutT
```
