---
title: アプリケーションの展開プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, deploying
- deploying [applications], how to
ms.assetid: 29486c37-6aa7-46fd-a457-916fd235f448
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a793b4abc1eb937cf24836b2bd21b6280c57a8bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985355"
---
# <a name="the-application-deployment-process"></a>アプリケーション展開プロセス
次の図に、BizTalk アプリケーションの展開に関連する一般的な手順を示します。 アプリケーションの展開の開発、テスト、ステージング、および運用フェーズ中に関連するタスクの詳細については、次を参照してください。[アプリケーション展開作業](../core/application-deployment-tasks.md)します。  
  
 ![アプリケーション展開プロセス](../core/media/appdeploymentprocess.gif "AppDeploymentProcess")  
  
1. **Visual Studio から BizTalk ソリューションのアセンブリを展開します。** これにより、アセンブリがビルドされ、アセンブリに含まれる ("アイテム" と呼ばれる) オーケストレーション、パイプライン、スキーマ、およびマップと共に、BizTalk 管理データベースにインポートされます。 また、展開により、アセンブリは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 内のプロジェクト プロパティで指定した BizTalk アプリケーションと関連付けられます。 手順については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。 ソリューションを展開したら、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールや BTSTask コマンドライン ツールを使用して、展開したアセンブリおよびそのアイテムを表示したり管理したりすることができます。 アイテムは、個別でもアプリケーション内でまとめたグループ単位でも管理できます。  
  
2. **追加し、成果物を構成します。** 管理コンソールまたは BTSTask を使用してアプリケーションには、スクリプトや Readme ファイルなどのアイテムを追加できます。 送信ポート、受信ポート、受信場所、オーケストレーションなどのアイテムを、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して構成することもできます。 詳細については、次を参照してください。[成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md)します。 参照してください[管理成果物](../core/managing-artifacts.md)します。 アプリケーションをインポートする環境ごとに異なるバインドを適用する場合には、バインド ファイルを生成してアプリケーションに追加することもできます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
3. **.Msi ファイルにアプリケーションをエクスポートします。** MSI ファイルのエクスポート ウィザードまたは BTSTask を使用して、アプリケーション アイテムを .msi ファイルにエクスポートできます。この .msi ファイルは、アプリケーションを実行するコンピューターにインストールしたり、アプリケーションを新しい BizTalk グループにインポートしたりするのに使用します。 手順については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。  
  
4. **別の BizTalk グループにアプリケーションをインポートし、それを実行するコンピューターにアプリケーションをインストールします。** MSI のインポート ウィザードまたは BTSTask を使用して、BizTalk アプリケーションを手順 3. で作成した .msi ファイルから別の BizTalk グループにインポートし、新しいグループにアプリケーションとそのアイテムを作成できます。 その後、.msi ファイルを使用して、アプリケーションを実行するコンピューターにアプリケーションをインストールできます。 これはアプリケーションの実行前に行ってください。 アプリケーションをテストする準備ができたら、テスト環境の BizTalk グループにアプリケーションをインポートおよびインストールすることができます。 アプリケーションがステージングまたは運用可能な状態になったら、いずれかの環境にアプリケーションをインポートおよびインストールすることができます。 手順については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。 参照してください[BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。  
  
5. **アプリケーションを起動し、正しく機能していることを確認します。** アプリケーションを起動することができます、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 」の説明に従って、管理コンソール[BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。 アプリケーションをテストすることができますし、 [BizTalk アプリケーション展開のテスト タスク](../core/testing-tasks-for-biztalk-application-deployment.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの展開と管理についてください。](../core/understanding-biztalk-application-deployment-and-management.md)   
 [BizTalk アプリケーションについて](../core/what-is-a-biztalk-application.md)