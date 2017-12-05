---
title: "VisualStudioHostRestart (アプリケーションの展開サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0b82627-1552-479d-a083-cdc9fe4843c3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d98a3a5e497a4476de897c8008f3a9976812209a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="visualstudiohostrestart-application-deployment-sample"></a>VisualStudioHostRestart (アプリケーションの展開サンプル)
このトピックでは、ローカル コンピュータの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で実行しているホスト インスタンスを再起動するための VisualStudioHostRestart サンプル スクリプトを使用する方法について説明します。 このスクリプトは、Visual Studio にアセンブリを再展開するときに使用できます。これにより、BizTalk Server ランタイムに変更内容がすぐに反映されます。 また、プロジェクトの展開のプロパティで設定できるオプションを使用して、ホスト インスタンスを再起動することもできます。 詳細については、次を参照してください。 [Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプル スクリプトは、次の処理を順番に実行します。  
  
1.  ローカル コンピュータのすべてのインプロセス ホスト インスタンスを停止します。  
  
2.  ローカル コンピュータのすべてのインプロセス ホスト インスタンスを開始します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 サンプルにありますが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次のように、インストール フォルダー: *\<サンプル パス\>*\Application Deployment\VisualStudioHostRestart です。  
  
 サンプルには、次のファイルが含まれています。  
  
-   RestartBizTalkHostInstances.vbs  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 次の手順に従って、このサンプルを実行します。  
  
### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
-   RestartBizTalkHostInstances.vbs を実行します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開 (BizTalk Server Samples フォルダ)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開します。](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)