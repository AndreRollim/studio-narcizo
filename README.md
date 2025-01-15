import React from 'react';
import { Instagram, Facebook, Mail, Menu, Phone, X } from 'lucide-react';
import { useState } from 'react';

const BeautySalon = () => {
  const [isMenuOpen, setIsMenuOpen] = useState(false);

  const toggleMenu = () => {
    setIsMenuOpen(!isMenuOpen);
  };

  return (
    <div className="min-h-screen flex flex-col">
      {/* Header */}
      <header className="bg-pink-100 p-4 fixed w-full top-0 z-50">
        <div className="container mx-auto flex justify-between items-center">
          <h1 className="text-2xl font-bold text-pink-600">Beleza Natural</h1>
          
          {/* Menu para Mobile */}
          <button onClick={toggleMenu} className="md:hidden">
            {isMenuOpen ? <X size={24} /> : <Menu size={24} />}
          </button>
          
          {/* Menu de Navegação */}
          <nav className={`${isMenuOpen ? 'flex' : 'hidden'} md:flex absolute md:relative top-16 md:top-0 left-0 w-full md:w-auto bg-pink-100 md:bg-transparent flex-col md:flex-row gap-4 p-4 md:p-0`}>
            <a href="#galeria" className="text-pink-800 hover:text-pink-600">Galeria</a>
            <a href="#sobre" className="text-pink-800 hover:text-pink-600">Sobre</a>
            <a href="#contato" className="text-pink-800 hover:text-pink-600">Contato</a>
          </nav>
        </div>
      </header>

      {/* Galeria de Fotos */}
      <section id="galeria" className="container mx-auto mt-24 p-4">
        <h2 className="text-3xl font-bold text-center mb-8">Nossa Galeria</h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
          {/* Placeholders para as fotos */}
          <img src="/api/placeholder/400/300" alt="Trabalho 1" className="w-full rounded-lg shadow-lg" />
          <img src="/api/placeholder/400/300" alt="Trabalho 2" className="w-full rounded-lg shadow-lg" />
          <img src="/api/placeholder/400/300" alt="Trabalho 3" className="w-full rounded-lg shadow-lg" />
          <img src="/api/placeholder/400/300" alt="Trabalho 4" className="w-full rounded-lg shadow-lg" />
          <img src="/api/placeholder/400/300" alt="Trabalho 5" className="w-full rounded-lg shadow-lg" />
          <img src="/api/placeholder/400/300" alt="Trabalho 6" className="w-full rounded-lg shadow-lg" />
        </div>
      </section>

      {/* Sobre */}
      <section id="sobre" className="bg-pink-50 py-16 mt-16">
        <div className="container mx-auto p-4">
          <h2 className="text-3xl font-bold text-center mb-8">Nossa História</h2>
          <div className="max-w-2xl mx-auto text-gray-700">
            <p className="mb-4">
              Com mais de 10 anos de experiência no mercado da beleza, nossa missão é realçar a beleza natural de cada cliente que passa por nosso salão.
            </p>
            <p className="mb-4">
              Especialistas em cortes modernos, coloração e tratamentos capilares, nossa equipe está sempre se atualizando com as últimas tendências e técnicas do mercado.
            </p>
            <p>
              Utilizamos produtos de primeira linha e oferecemos um ambiente acolhedor onde você pode relaxar e se sentir especial.
            </p>
          </div>
        </div>
      </section>

      {/* Footer com Contatos */}
      <footer id="contato" className="bg-pink-800 text-white mt-auto">
        <div className="container mx-auto p-8">
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
            <div>
              <h3 className="text-xl font-bold mb-4">Horário de Funcionamento</h3>
              <p>Segunda a Sábado</p>
              <p>09:00 - 19:00</p>
            </div>
            
            <div>
              <h3 className="text-xl font-bold mb-4">Endereço</h3>
              <p>Rua das Flores, 123</p>
              <p>Centro - São Paulo</p>
            </div>
            
            <div>
              <h3 className="text-xl font-bold mb-4">Contato</h3>
              <p className="flex items-center gap-2">
                <Phone size={16} />
                (11) 99999-9999
              </p>
              <p className="flex items-center gap-2">
                <Mail size={16} />
                contato@belezanatural.com
              </p>
            </div>
            
            <div>
              <h3 className="text-xl font-bold mb-4">Redes Sociais</h3>
              <div className="flex gap-4">
                <a href="#" className="hover:text-pink-300"><Instagram size={24} /></a>
                <a href="#" className="hover:text-pink-300"><Facebook size={24} /></a>
                <a href="#" className="hover:text-pink-300"><Mail size={24} /></a>
              </div>
            </div>
          </div>
          
          <div className="text-center mt-8 pt-8 border-t border-pink-700">
            <p>&copy; 2025 Beleza Natural. Todos os direitos reservados.</p>
          </div>
        </div>
      </footer>
    </div>
  );
};

export default BeautySalon;