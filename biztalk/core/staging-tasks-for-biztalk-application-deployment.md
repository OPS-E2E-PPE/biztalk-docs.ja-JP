---
title: "BizTalk アプリケーション展開のステージング作業 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, staging
- deploying [applications], staging
- applications, deploying
- deploying [applications], tasks
ms.assetid: de60eddb-da13-412a-94f9-331387b5930e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f03d0cfd5db587a84a080d5963d6696e123ef2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="staging-tasks-for-biztalk-application-deployment"></a>BizTalk アプリケーション展開のステージング作業
BizTalk アプリケーションをステージング環境に展開するための手順を次に示します。  
  
1.  **.Msi ファイルをステージング環境にコピーします。** 」の説明に従って[BizTalk アプリケーション展開のテスト タスク](../core/testing-tasks-for-biztalk-application-deployment.md)BizTalk アプリケーションは、テストが完了し、ステージングの準備ができて、テスト チームは、1 つまたは複数の .msi ファイルをステージングするとします。 完全なソリューションは 1 つ以上の BizTalk アプリケーションで構成されるので、複数の .msi ファイルを受け取る場合があります。この .msi ファイルをステージング コンピューターにコピーし、次に示す手順に従って、BizTalk アプリケーションを .msi ファイルからステージング環境の BizTalk グループにインポートできます。 また、.msi ファイルを使用して、アプリケーションを実行するコンピューターにアプリケーションをインストールすることもできます。  
  
2.  **.Msi ファイルからアプリケーションをインポートします。** BizTalk Server 管理コンソールから利用できるインポート ウィザードを使用して、.msi ファイルのコンテンツをステージング環境の BizTalk グループのアプリケーションにインポートできます。 詳細については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。 指定されているアプリケーションが存在しない場合は、.msi ファイルをインポートすることによって作成されます。 その後は、BizTalk Server 管理コンソールでアプリケーションを表示し、その構成や内容を変更できます。 この操作は、ステージング環境用にバインドを変更する場合などに必要になります。 詳細については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)です。 バインド ファイルがステージング環境に適したバインドをアプリケーションに追加された場合は、インポート処理中に、バインドを適用できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
3.  **バインド ファイルをエクスポートし、(省略可能) アプリケーションに再度追加します。** アプリケーションを変更または追加する場合にアプリケーションをステージング環境に後で簡単に再インポートできるようにするには、アプリケーションのバインドをエクスポートし、バインドの対象となるステージング環境を指定してアプリケーションに再度追加します。 アプリケーションの .msi ファイルをステージング環境の BizTalk Server に後で再インポートするときに、これらのバインドを適用するように指定できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
4.  **アプリケーションをインストールします。** アプリケーションを実行するすべてのコンピューターに、アプリケーションをインストールできます。 アプリケーションは、インストール ウィザードを使用するか、単純に .msi ファイルをダブルクリックすることによって、インストールできます。 詳細については、次を参照してください。[を BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)です。  
  
5.  **アプリケーションをテストして、構成とバインディングを確認してください。** アプリケーションをテストして、意図したとおりにステージング環境でアプリケーションが機能するかどうかを確認できます。 ユーザーまたは開発者が必要な変更を行った後で、手順 1. ～ 4. を再実行できます。  
  
6.  **実稼働環境へのアプリケーションを展開するための .msi を生成**です。 実稼働環境用に BizTalk アプリケーションの構成を完了し、構成を確認したら、そのアプリケーションを実稼働環境に展開できます。 これを行うには、ウィザードを使用する、エクスポート、新しい .msi ファイルを生成する」の説明に従って[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。 その後で、実稼働環境の展開を担当する IT 管理者に .msi ファイルを渡すことができます。 IT 管理者は、」の説明に従って、それを実行するコンピューターにインストールするとともに、アプリケーションを実稼働コンピューターに BizTalk Server にインポートする .msi ファイルを使用して、[運用展開のタスクを BizTalk アプリケーション](../core/production-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開タスク](../core/application-deployment-tasks.md)