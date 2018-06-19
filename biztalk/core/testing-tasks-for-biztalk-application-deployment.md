---
title: BizTalk アプリケーションの展開のテスト作業 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], testing
- testing, deploying
- testing, tasks
ms.assetid: fb043755-6d01-4ceb-b189-5a5f286c2b37
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfd4385c4de076c8c89b409177204ee8fce5548b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279714"
---
# <a name="testing-tasks-for-biztalk-application-deployment"></a>BizTalk アプリケーション展開のテスト作業
BizTalk アプリケーションのアイテムをテストおよびデバッグのためテスト環境に展開する手順を次に示します。  
  
1.  **.Msi ファイルをテスト環境にコピーします。** 」の説明に従って[BizTalk アプリケーション展開の開発タスク](../core/development-tasks-for-biztalk-application-deployment.md)BizTalk アプリケーションをテストする準備がときに、開発者がアプリケーションのアイテムを .msi ファイルにエクスポートします。 完全なソリューションは 1 つ以上の BizTalk アプリケーションで構成されるので、複数の .msi ファイルをテスト用に受け取る場合があります。 .msi ファイルをテスト用コンピューターにコピーした後、次の手順で説明するように、.msi ファイルから BizTalk Server にアイテムをインポートできます。 また、.msi ファイルを使用するには、それらを実行するコンピューターにアプリケーションをインストールします。  
  
2.  **.Msi ファイルからアプリケーションをインポートします。** BizTalk Server 管理コンソールから利用できるインポート ウィザードを使用して、.msi ファイルに含まれるアイテムを BizTalk Server の現在のインスタンス上のアプリケーションにインポートできます。 詳細については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。 指定したアプリケーションが存在しない場合は、インポート プロセスによって作成されます。 その後は、BizTalk Server 管理コンソールでアプリケーションを表示し、その構成や内容を変更できます。 この操作は、テスト環境用にバインドを変更する場合などに必要になります。 詳細については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)です。 テスト環境に適したバインドを含むバインド ファイルをアプリケーションに追加してある場合は、インポート プロセスでそのバインドを適用できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
3.  **アプリケーションをインストールします。** これで、アプリケーションを実行するサーバーにアプリケーションをインストールすることができます。 アプリケーションにファイル ベースのアイテムが含まれる場合は、それもインストールする必要があります。インストールしないと機能しません。 アプリケーションは、.msi file をダブルクリックしてインストールできます。 これにより、アプリケーションのアイテムがローカル コンピューターにインストールおよび登録され、アプリケーションを実行できるようになります。 詳細については、次を参照してください。[を BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)です。  
  
4.  **アプリケーションをテストします。** これで、アプリケーションをテストすることができます。 テスト時に検出したバグが開発者によって修正され、更新済みの .msi ファイルが手元に届いたら、手順 1.、2.、3. を再び実行します。  
  
5.  **バインド ファイルをエクスポートし、(省略可能) アプリケーションに再度追加します。** 後で変更や追加をテストする必要がある場合にテスト環境にアプリケーションを簡単に再インポートできるようにするには、アプリケーションのバインドをエクスポートし、バインドの対象となるテスト環境を指定してアプリケーションに再度追加します。 アプリケーションの .msi ファイルをテスト環境の BizTalk Server に後で再インポートするときに、これらのバインドを適用するように指定できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
6.  **ステージング環境にアプリケーションを展開するための .msi を生成**です。 テストが終了した BizTalk アプリケーションは、ステージング環境に展開できます。 これを行うには、ウィザードを使用する、エクスポート、新しい .msi ファイルを生成するのに手順 2 で前述したようです。 ステージング環境のデプロイを担当する IT 管理者には、.msi ファイルから渡すことができます。 IT 管理者は、ステージング コンピューターにアプリケーションを BizTalk Server にインポートし、」の説明に従って、それを実行するコンピューターにアプリケーションをインストールする .msi ファイルを使用[ステージング展開のタスクを BizTalk アプリケーション](../core/staging-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開タスク](../core/application-deployment-tasks.md)