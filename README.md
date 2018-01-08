# Open Hardware Construction Platform - C++ API

Reference implementation of OHCP in C++

    class adder : public module {
        virtual int build() {
            node & a = *this->create_port("a", port::in, type::array(logic, WIDTH));      // Add a port to the module
            node & b = *this->create_port("b", port::in, type::array(logic, WIDTH));
            node * c;
            if (add_3) {                                            // Conditionally add port
                c = this->create_port("b", port::in, type::array(logic, WIDTH));
            }
            node & o = *this->create_port("o", port::out, type::array(logic, WIDTH));
            
            if (add_3) {
                o = a + b + c;
            } else {
                o = a + b;
            }
            
            return 0;
        }
    }
    
    int main() {
        module * a0 = module::create<adder>("a0");
        
        dump_sysverilog(a0, "file.sv");
    }

## Acknowledgments

_I humbly present this work to The Supreme Protector who resides in the beautiful temple at the heart of Guruvayur town_

_Special thanks to my parents, my uncle and my cousin for their support in my scientific endeavors_

## About

*Work in progress*
