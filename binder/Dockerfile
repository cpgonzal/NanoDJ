FROM cpgonzal/nanodj:latest

WORKDIR /home/jovyan/notebooks

RUN git init && \
    git remote add origin -f https://github.com/cpgonzal/NanoDJ && \
    git config core.sparseCheckout true && \
    echo "nanodj_notebooks/" >> .git/info/sparse-checkout && \
    git pull origin master && \
    mv nanodj_notebooks/* . && \
    rm -rf .git nanodj_notebooks/ && \
    chown -R jovyan:users ~/notebooks 


USER jovyan
CMD jupyter lab --allow-root
