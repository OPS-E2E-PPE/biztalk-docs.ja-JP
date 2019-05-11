---
title: BizTalk アプリケーション展開のタスクのテスト |Microsoft Docs
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
ms.openlocfilehash: f1104e2cc1a25d0c0b91f990c6c8ef5969c2e7c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299014"
---
# <a name="testing-tasks-for-biztalk-application-deployment"></a>BizTalk アプリケーション展開のテスト タスク
テストとデバッグ用のテスト環境に BizTalk アプリケーションのアイテムを展開するための手順を次に示します。  
  
1.  **テスト環境に .msi ファイルをコピーします。** 」の説明に従って[BizTalk アプリケーション展開の開発タスク](../core/development-tasks-for-biztalk-application-deployment.md)BizTalk アプリケーションがテスト、準備ができたとき、開発者がアプリケーションのアイテムを .msi ファイルにエクスポートします。 完全なソリューションは可能性がありますの 1 つまたは複数の BizTalk アプリケーションで構成されるので、テストに複数の .msi ファイルを受信する可能性があります。 テスト用コンピューターに .msi ファイルをコピーし、その後、次の手順」の説明に従って、成果物、.msi ファイルから BizTalk Server にインポートできます。 .Msi ファイルを使用しても、それらを実行するコンピューターにアプリケーションをインストールします。  
  
2.  **アプリケーションを .msi ファイルからインポートします。** BizTalk Server 管理コンソールから利用できるインポート ウィザードを使用して、BizTalk Server の現在のインスタンス上のアプリケーションを .msi ファイル内のアイテムをインポートすることができます。 詳細については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。 指定したアプリケーションが存在しない場合、インポート プロセスを作成します。 アプリケーションを表示し、その構成や、BizTalk Server 管理コンソールから内容を変更することができます。 たとえば、テスト環境のバインドを変更することがあります。 詳細については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)します。 バインド ファイルは、テスト環境を適切なバインディングをアプリケーションに追加された場合、は、インポート処理中に、バインドを適用できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
3.  **アプリケーションをインストールします。** アプリケーションを実行するサーバー上でアプリケーションをインストールできます。 アプリケーションには、ファイル ベースのアイテムが含まれている場合は、インストールする必要があります。 または機能しません。 アプリケーションをインストールするには、.msi ファイルをダブルクリックします。 これにより、インストールし、アプリケーションが実行できるように、ローカル コンピューター上のアプリケーションのアイテムを登録します。 詳細については、次を参照してください。 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。  
  
4.  **アプリケーションをテストします。** アプリケーションをテストすることができます。 開発者は、表示されているすべてのバグを修正し、更新済みの .msi ファイルを使用できます後、は、1、2、および 3 の手順をもう一度実行できます。  
  
5.  **バインド ファイルをエクスポートし、(省略可能) のアプリケーションに再度追加します。** 変更または追加をテストする必要がある場合は後で、テスト環境にアプリケーションをインポートしやすいように、可能性がある、アプリケーションのバインドをエクスポートし、アプリケーションに再度追加のテストのターゲット環境を指定します。バインドします。 テスト環境で BizTalk Server に後でアプリケーションの .msi ファイルをインポートする場合は、これらのバインドが適用されることを指定できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
6.  **ステージング環境にアプリケーションをデプロイするための .msi を生成**します。 BizTalk アプリケーションのテストが完了したらは、ステージング環境にデプロイできます。 これを行うには、使用するエクスポート ウィザード新しい .msi ファイルを生成するのに手順 2 で前述したようです。 ステージング環境のデプロイを担当する IT 管理者には、.msi ファイルから渡すことができます。 IT 管理者は、ステージング コンピューターでアプリケーションを BizTalk Server にインポートし、」の説明に従って、実行するコンピューターでアプリケーションをインストールする .msi ファイルを使用[BizTalk アプリケーション展開のタスクをステージング](../core/staging-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開作業](../core/application-deployment-tasks.md)