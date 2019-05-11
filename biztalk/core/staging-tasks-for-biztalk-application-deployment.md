---
title: BizTalk アプリケーション展開のステージング タスク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, staging
- deploying [applications], staging
- applications, deploying
- deploying [applications], tasks
ms.assetid: de60eddb-da13-412a-94f9-331387b5930e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e221e34b4e493fdb5ba112ad389d298accde2d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398931"
---
# <a name="staging-tasks-for-biztalk-application-deployment"></a>BizTalk アプリケーション展開のステージング作業
ステージング環境に BizTalk アプリケーションの展開に必要な手順を次に示します。  
  
1.  **ステージング環境に .msi ファイルをコピーします。** 」の説明に従って[BizTalk アプリケーション展開のテスト タスク](../core/testing-tasks-for-biztalk-application-deployment.md)BizTalk アプリケーションは、テストが完了し、ステージングの準備ができて、テスト チーム、1 つまたは複数の .msi ファイルをステージング環境の場合に、します。 (完全なソリューションがで構成される 1 つまたは複数の BizTalk アプリケーションののでステージに複数の .msi ファイルを受信する可能性があります。)この .msi ファイルをステージング コンピューターにコピーし、次に、次の手順」の説明に従って、BizTalk アプリケーション、.msi ファイルからインポートをステージング環境で BizTalk グループにできます。 また、.msi ファイルを使用するには、アプリケーションを実行するコンピューターにアプリケーションをインストールします。  
  
2.  **アプリケーションを .msi ファイルからインポートします。** BizTalk Server 管理コンソールから利用できるインポート ウィザードを使用して、ステージング環境での BizTalk グループにアプリケーションを .msi ファイルの内容をインポートすることができます。 詳細については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。 指定したアプリケーションが存在しない場合を作成、.msi ファイルをインポートします。 アプリケーションを表示し、その構成や、BizTalk Server 管理コンソールから内容を変更することができます。 たとえば、ステージング環境のバインドを変更することがあります。 詳細については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)します。 場合、ステージング環境用の適切なバインドが、アプリケーション、バインド ファイルが追加され、インポート処理中に、バインドを適用できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
3.  **バインド ファイルをエクスポートし、(省略可能) のアプリケーションに再度追加します。** アプリケーションに変更または追加を加えた場合は後で、ステージング環境にアプリケーションをインポートしやすいように、たい場合があります、アプリケーションのバインドをエクスポートし、アプリケーションに再度追加して、ステージング環境のターゲットを指定します。バインドの環境です。 ステージング環境で BizTalk Server に後でアプリケーションの .msi ファイルをインポートする場合は、これらのバインドが適用されることを指定できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
4.  **アプリケーションをインストールします。** すべてのアプリケーションを実行するコンピューターでアプリケーションをインストールできます。 インストール ウィザードを使用して、.msi ファイルをダブルクリックするだけでアプリケーションをインストールすることができます。 詳細については、次を参照してください。 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。  
  
5.  **構成とバインディングを確認するアプリケーションをテストします。** ステージング環境で期待どおりに機能しているかどうかを確認するアプリケーションをテストすることができます。 ユーザーまたは開発者は、必要な変更を行った後、は、手順 1. ~ 4. をもう一度に従ってできます。  
  
6.  **運用環境にアプリケーションをデプロイするための .msi を生成**します。 運用環境の BizTalk アプリケーションの構成が完了し、構成を確認したら後、は、運用環境にデプロイできます。 これを行うには、ウィザードを使用する、エクスポート、新しい .msi ファイルを生成する」の説明に従って[BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。 運用環境のデプロイを担当する IT 管理者には、.msi ファイルから渡すことができます。 IT 管理者は」の説明に従って、それを実行するコンピューターにインストールするほか、運用コンピューターでアプリケーションを BizTalk Server にインポートする .msi ファイルを使用[BizTalkアプリケーションの展開の実稼働作業](../core/production-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開作業](../core/application-deployment-tasks.md)