FROM cpgonzal/nanodj:latest

WORKDIR /home/jovyan/notebooks

RUN git init && \
    git remote add origin -f https://github.com/cpgonzal/NanoDJ && \
    git pull origin binder
    git config core.sparseCheckout true && \
    echo '/*' >> .git/info/sparse-checkout && \
    echo '!README.md' >> .git/info/sparse-checkout && \
    echo 'nanodj_notebooks/data' >> .git/info/sparse-checkout && \
    git pull origin master && \
    mv nanodj_notebooks/* . && \
    rm -rf .git nanodj_notebooks/ && \
 
    git pull origin binder && \
    chown -R jovyan:users ~/notebooks 


USER jovyan
CMD jupyter lab --allow-root
