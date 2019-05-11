---
title: VisualStudioHostRestart (アプリケーションの展開サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0b82627-1552-479d-a083-cdc9fe4843c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96cc470bde0ca8b62a25de81a272d2cf8a891971
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320825"
---
# <a name="visualstudiohostrestart-application-deployment-sample"></a>VisualStudioHostRestart (アプリケーションの展開サンプル)
このトピックでは、VisualStudioHostRestart サンプル スクリプトを使用して、実行されているホスト インスタンスを再起動する方法を説明します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、ローカル コンピューター上です。 BizTalk Server ランタイムはすぐに、変更が取得するように、Visual Studio でアセンブリを再デプロイする場合は、このスクリプトを使用することができます。 また、プロジェクトの配置プロパティで設定できるは、ホスト インスタンスを再起動するのにオプションを使用することができます。 詳細については、次を参照してください。 [Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプル スクリプトでは、順序で、次の操作を実行します。  
  
1.  ローカル コンピューターのすべてのインプロセス ホスト インスタンスを停止します。  
  
2.  ローカル コンピューターのすべてのインプロセス ホスト インスタンスを開始します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール フォルダーに格納されています*\<サンプル パス\>* \Application Deployment\VisualStudioHostRestart します。  
  
 サンプルには、次のファイルが含まれています。  
  
-   RestartBizTalkHostInstances.vbs  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 次の手順に従って、このサンプルを実行します。  
  
### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
-   RestartBizTalkHostInstances.vbs を実行します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開 (BizTalk Server Samples フォルダー)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)