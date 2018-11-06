FROM cpgonzal/nanodj:latest

WORKDIR /home/jovyan/notebooks

RUN git init && \
    git remote add origin -f https://github.com/cpgonzal/NanoDJ && \
    git pull origin binder && \
    rm -rf .git && \
    chown -R jovyan:users ~/notebooks 


USER jovyan
CMD jupyter lab --allow-root
