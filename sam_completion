_sam(){
  local cur prev cword
  _get_comp_words_by_ref -n : cur prev cword

  COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )

  # sam <second word>
  if [ "${cword}" -eq 1 ]; then
    COMPREPLY=( $(compgen -W "local validate package deploy help" -- "${cur}") )
    return 0
  fi

  # sam deploy/local/package/validate <third word>
  if [ "${cword}" -eq 2 ]; then

      # -----------------------
      # sam deploy <third word>
      # -----------------------
      if [ "${prev}" = "deploy" ]; then
        comp="--template-file --stack-name --parameter-overrides --capabilities --no-execute-changeset --role-arn --notification-arns help"
        COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
      fi

      # -----------------------
      # sam local <third word>
      # -----------------------
      if [ "${prev}" = "local" ]; then
        comp="start-api invoke generate-event help"
        COMPREPLY=( $(compgen -W "${comp}" -- "${cur}") )
      fi

      # -----------------------
      # sam package <third word>
      # -----------------------
      if [ "${prev}" = "package" ]; then
        comp="--template-file --s3-bucket --s3-prefix --kms-key-id --output-template-file --use-json --force-upload"
        COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
      fi

      # -----------------------
      # sam validate <third word>
      # -----------------------
      if [ "${prev}" = "validate" ]; then
        COMPREPLY=( $(compgen -f -- "${cur}") )
      fi
  fi

  if [ "${cword}" -eq 3 ]; then
      # ----------------------------
      # sam local <etc> <forth word>
      # ----------------------------
      # sam local generate-event <forth word>
      if [ "${prev}" = "generate-event" ]; then
        comp="s3 sns kinesis dynamodb api schedule -help"
        COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
      fi
      # sam local invoke <forth word>
      if [ "${prev}" = "invoke" ]; then
        comp="--template --parameter-values --log-file --env-vars --event --debug-port --docker-volume-basedir --docker-network --skip-pull-image --profile"
        COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
      fi
      # sam local start-api <forth word>
      if [ "${prev}" = "start-api" ]; then
        comp="--template --parameter-values --log-file --static-dir --port --host --env-vars --debug-port --docker-volume-basedir --docker-network --skip-pull-image --profile --prefix-routing"
        COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
      fi
  fi

  if [ "${prev}" = "--template" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--parameter-values" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--log-file" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--static-dir" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--port" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--host" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--env-vars" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--debug-port" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--docker-volume-basedir" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--docker-network" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--profile" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--template-file" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--stack-name" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--parameter-overrides" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--capabilities" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--no-execute-changeset" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--role-arn" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--notification-arns" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  elif [ "${prev}" = "--role-arn" ]; then
    COMPREPLY=( $(compgen -f -- "${cur}") )
  fi

  if [ "${prev}" = "s3" ]; then
    comp="--region --bucket --key"
    COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
  elif [ "${prev}" = "kinesis" ]; then
    comp="--region --partition --sequence --data"
    COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
  elif [ "${prev}" = "dynamodb" ]; then
    comp="--region"
    COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
  elif [ "${prev}" = "api" ]; then
    comp="--method --body --resource --path"
    COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
  elif [ "${prev}" = "schedule" ]; then
    comp="--region"
    COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
  elif [ "${prev}" = "sns" ]; then
    comp="--message --topic --subject"
    COMPREPLY=( $(compgen -W "${comp}" -f -- "${cur}") )
  fi




}

complete -F _sam sam
