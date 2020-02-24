




just to capture this...

---

julia from scratch on stretch

    sudo apt-get install build-essential libatomic1 python gfortran perl wget m4 cmake pkg-config
    git clone git://github.com/JuliaLang/julia.git
    cd julia
    git checkout v1.3.1
    export CXXFLAGS="-D_GLIBCXX_USE_CXX11_ABI=0"
    make

followed by ./julia

    using Pkg
    Pkg.add("IJulia")
    Pkg.build("IJulia")
    Pkg.precompile()

and now Julia kernels show up in jupyerlab for AI Platform Notebooks.

Could also just download the dist tarballs
[linux-x86](https://julialang-s3.julialang.org/bin/linux/x64/1.3/julia-1.3.1-linux-x86_64.tar.gz)
with
[hashes](https://julialang-s3.julialang.org/bin/linux/x64/1.3/julia-1.3.1-linux-x86_64.tar.gz.asc).

Check sigs

    echo "$(cat archive.tar.gz.sha256) archive.tar.gz" | sha256sum --check --status

Or we can prolly find a ppa...

---

    https://colab.research.google.com/drive/1zAkadxc_iJE_oj-TOdwHpfLU2oaNHJOS#scrollTo=cEOANYIVIdR5

