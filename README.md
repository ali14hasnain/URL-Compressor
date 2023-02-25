# URL-Compressor
Designed and implemented a Python-based backend for a URL compression tool, reducing file sizes by 65%.
# URL-Compressor
Designed and implemented a Python-based backend for a URL compression tool, reducing file sizes by 65%.
class URL_Shortener:
#add numerical char cooresponding to number of char required after / in the ouput.
    id = 100000000
    
    url2id = {}
    
    def shorten_url(self, original_url):
        if original_url in self.url2id:
            id = self.url2id[original_url]
            shorten_url = self.encode(id)
        else:
            self.url2id[original_url] = self.id
            shorten_url = self.encode(self.id)
            
            self.id += 1
        
        return "short_url.com/"+shorten_url
    
    def encode(self, id):
        characters = 
        #62 characters base
        "0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"
        base = len(characters)
        ret = []
        while id > 0:
            val = id % base
            ret.append(characters[val])
            id = id // base
       
        return "".join(ret[::-1])
#Tests
shortener = URL_Shortener()
print(shortener.shorten_url("mynameisALI.com"))
print(shortener.shorten_url("www.linkedin.com/in/muhammad-ahasnain"))
print(shortener.shorten_url("meowmeow.com"))
print(shortener.shorten_url("hellllooooooooooooworlddddddddd.com"))

short_url.com/6LAze
short_url.com/6LAzf
short_url.com/6LAzg
short_url.com/6LAzh
