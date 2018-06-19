---
title: BizTalk アプリケーションの展開の実稼働作業 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], assemblies
- applications, deploying
- assemblies, warnings
- deploying [applications], warnings
- deploying [applications], tasks
- assemblies, deploying
- deploying [applications], production
ms.assetid: e77d8921-42ef-4c51-aab2-66c086aad955
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 260afd4522d28bdd2a485a1a11edc045c7fde880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265034"
---
# <a name="production-tasks-for-biztalk-application-deployment"></a>BizTalk アプリケーション展開の実稼働作業
BizTalk アプリケーションを実稼働環境に展開するための手順を次に示します。  
  
> [!IMPORTANT]
>  実稼働コンピューターの Visual Studio からアセンブリを展開することはできません。 再展開を可能にするため、Visual Studio では同じまたは別のアプリケーション内に存在するアセンブリの展開解除、バインド解除、停止、および参加解除が行われる可能性があります。 これは開発環境では必要であり適切なことですが、実稼働環境では予期しない結果や結果や好ましくない結果を引き起こす可能性があります。 また、実稼働コンピューター上の Visual Studio からアセンブリが展開される危険性を回避するために、実稼働コンピューターには Visual Studio をインストールしないことをお勧めします。  
  
> [!IMPORTANT]
>  実稼働環境で他のアプリケーションが依存しているアプリケーションを更新する場合は、実行中の他のアプリケーションを中断しないように注意してください。 詳細については、次を参照してください。[更新アプリケーション用の重要な考慮事項](../core/important-considerations-for-updating-applications.md)です。  
  
1.  **.Msi ファイルを実稼働環境にコピーします。** 」の説明に従って[BizTalk アプリケーション展開のテスト タスク](../core/testing-tasks-for-biztalk-application-deployment.md)アプリケーションがステージングが完了し、実稼働、ステージング構成を担当する IT 管理者は、BizTalk に .msi ファイルを提供する場合、運用環境のデプロイに使用します。 この .msi ファイルを実稼働コンピューターにコピーし、次に示す手順に従って、BizTalk アプリケーションを .msi ファイルから BizTalk Server にインポートできます。 また、.msi ファイルを使用して、アプリケーションを実行するコンピューターにアプリケーションをインストールすることもできます。 完全な BizTalk ソリューションは 1 つまたは複数のアプリケーションで構成されるので、展開用に受け取る .msi ファイルは複数存在する場合もあります。  
  
2.  **.Msi ファイルからアプリケーションをインポートします。** BizTalk Server 管理コンソールから利用できるインポート ウィザードを使用して、.msi ファイルのコンテンツを BizTalk Server の現在のインスタンス上のアプリケーションにインポートできます。 詳細については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。 指定されているアプリケーションが存在しない場合は、.msi ファイルをインポートすることによって作成されます。 その後は、管理コンソールでアプリケーションを表示し、その構成や内容を変更できます。 この操作を行う必要があるのは、証明書やエンドポイント (URL など) を構成したり、実稼働環境用にバインドを変更する場合などです。 詳細については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)です。 実稼働環境に対応するバインドを定義したバインド ファイルがアプリケーションに追加された場合は、インポート プロセスでそのバインドを適用できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
3.  **インストールし、アプリケーションを起動します。** アプリケーションを実行するすべてのコンピューターにアプリケーションをインストールし、管理コンソールでアプリケーションを起動できます。 アプリケーションは、.msi file をダブルクリックしてインストールできます。 詳細については、次を参照してください。[を BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)です。  
  
4.  **バインド ファイルをエクスポートし、(省略可能) アプリケーションに再度追加します。** 後で変更や追加を展開する必要がある場合に実稼働環境にアプリケーションを簡単に再インポートできるようにするには、アプリケーションのバインドをエクスポートし、バインドの対象となる実稼働環境を指定してアプリケーションに再度追加します。 アプリケーションの .msi ファイルを実稼働環境の BizTalk Server に後で再インポートするときに、これらのバインドが適用されるように指定できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
5.  **(省略可能) 新しい .msi ファイルにアプリケーションをエクスポートします。** 構成の変更や、アプリケーションへの追加を行い (たとえば他の BizTalk グループにアプリケーションを配置するなど)、.msi ファイルに反映されるまでに変更する場合場合、」の説明に従って、新しい .msi ファイルをエクスポートできます[エクスポートする方法、BizTalk アプリケーション](../core/how-to-export-a-biztalk-application.md)です。  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開タスク](../core/application-deployment-tasks.md)