FROM althack/ros2:humble-dev 


# set timezone
ENV TZ="Europe/Berlin"

# [Optional] Uncomment this section to install additional packages. **
#
# ENV DEBIAN_FRONTEND=noninteractive
# RUN apt-get update \
#   && apt-get -y install --no-install-recommends <your-package-list-here> \
#   #
#   # Clean up
#   && apt-get autoremove -y \
#   && apt-get clean -y \
#   && rm -rf /var/lib/apt/lists/*
# ENV DEBIAN_FRONTEND=dialog

# Set up auto-source of workspace for ros user
ARG WORKSPACE
RUN echo "if [ -f ${WORKSPACE}/install/setup.bash ]; then source ${WORKSPACE}/install/setup.bash; fi" >> /home/ros/.bashrc \
#  && echo "export ROS_DISCOVERY_SERVER=';127.0.0.1:65118'" >> /home/ros/.bashrc \
  && echo "export ROS_LOCALHOST_ONLY=0" >> /home/ros/.bashrc \
  && echo "alias ros=ros2" >> /home/ros/.bashrc

WORKDIR $WORKSPACE
USER ros
# default CMD to startup container
CMD /bin/sh -c "while sleep 1000; do :; done"
