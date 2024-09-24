/*** MADE BY FREENZYSG ***/
/*
- https://dsc.gg/your-http
- .FreenzySG.#2331
- Contributor : asianzx, naZlatan, arlemons
*/

// Requirements
const readline = require("readline")
const exetitle = require("console-title")
const rl = readline.createInterface({ input: process.stdin, output: process.stdout })
const os = require("os")
const fs = require("fs")
const _cp = require('child_process')
function writeLogs(character) {
	fs.appendFileSync(`./gtps-launcher-logs/${namaserver}.txt`, `\n${character} | ${month}-${date} | ${hours}:${minutes}\n`)
}
function isthatLetter(character) {
	try {
    	eval("let " + character + ";");
    	let regExSpecial = /[^\$_]/;
        	return regExSpecial.test(character);
  	} catch (error) {
        	return false;
  	}
}
// current timestamp in milliseconds
let date_ob = new Date();
// adjust 0 before single digit date
let date = ("0" + date_ob.getDate()).slice(-2);
// current month
let month = ("0" + (date_ob.getMonth() + 1)).slice(-2);
// current year
let year = date_ob.getFullYear();
// current hours
let hours = date_ob.getHours();
// current minutes
let minutes = date_ob.getMinutes();
// current seconds
let seconds = date_ob.getSeconds();
const normaldata = `# Copyright (c) 1993-2009 Microsoft Corp.
#
# This is a sample HOSTS file used by Microsoft TCP/IP for Windows.
#
# This file contains the mappings of IP addresses to host names. Each
# entry should be kept on an individual line. The IP address should
# be placed in the first column followed by the corresponding host name.
# The IP address and the host name should be separated by at least one
# space.
#
# Additionally, comments (such as these) may be inserted on individual
# lines or following the machine name denoted by a '#' symbol.
#
# For example:
#
#  	102.54.94.97 	rhino.acme.com      	# source server
#   	38.25.63.10 	x.acme.com          	# x client host
 
# localhost name resolution is handled within DNS itself.
#  	127.0.0.1   	localhost
#  	::1         	localhost`
// Saving offline data - arlemons
if(fs.existsSync('build_cfg.json')) {
const { server_ip, server_name, server_region } = require('./build_cfg.json')
exetitle(`${server_name} / ${server_ip} / ${server_region}`)
console.log(`

██ 	██ ███████ ██   	██████  ██████  ███	███ ███████
██ 	██ ██  	██  	██  	██	██ ████  ████ ██ 	 
██  █  ██ █████   ██  	██  	██	██ ██ ████ ██ █████   
██ ███ ██ ██  	██  	██  	██	██ ██  ██  ██ ██ 	 
 ███ ███  ███████ ███████  ██████  ██████  ██  	██ ███████
                                                         	 
                                                         	 
`)
// Some desgin and main pages - frenzy
console.log(`--- This Program is Open Sourced ---
Visit : https://github.com/FrenzY8/growtopia-private-server-launcher
for get the source

1 : Join ${server_name}
2 : Exit ${server_name}
3 : Join your own server (edit own IPs)`)
rl.question("Answer> ", jawaban => {

	if(!jawaban) { // No answer given - frenzy
    	console.log("You must given a valid answer.")
    	return;
	}

	if (jawaban == "1") { // Joining to a server - naZlatan
    	const pathhost = `C:/Windows/System32/drivers/etc/hosts`
    	// fs.unlinkSync(pathhost)
    	console.log(`Joining ${server_name}.. just wait about 3 seconds...`)
    	setTimeout(function(waitAsecond) {
    	try {
        	console.log(`Succes Joining ${server_name}`)
        	fs.writeFileSync(pathhost, `${normaldata}\n${server_ip} growtopia1.com\n${server_ip} growtopia2.com`)
        	_cp.execFile(`${os.homedir()}/AppData/Local/Growtopia/Growtopia.exe`).on('close', (e, shutdown) => {
            	writeLogs(`Succes Joining ${server_name}`)
            	if(e) {
                	// Missing permission - naZlatan
                	console.log("--- Please run this program as administrator! ---")
                	return;
            	}
            	if(shutdown) {
                	console.log("shutdowning.")
                	return;
            	}
            	console.log("Growtopia closed!")
        	})
    	} catch(noPermission) {
        	console.log("--- Please run this program as administrator. ---")
        	console.log(noPermission)
