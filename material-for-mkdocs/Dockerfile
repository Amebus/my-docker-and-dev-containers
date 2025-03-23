FROM squidfunk/mkdocs-material
RUN pip install mkdocs-git-revision-date-localized-plugin
RUN apk add  --no-cache \
		git

# COPY /docker-image-files/mkdoc-serve /docs

ENTRYPOINT [ "/bin/sh", "-c" ]
CMD [ "sh" ]