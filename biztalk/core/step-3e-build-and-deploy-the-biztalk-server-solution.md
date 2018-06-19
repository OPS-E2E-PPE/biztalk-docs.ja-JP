---
title: 'ステップ 3 e: ビルドし、BizTalk Server ソリューションの配置 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfc382b-ed4a-4401-9343-be1bffd747c9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a970a8f7adb450156b89849eb986c84fd05ab55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276626"
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a>ステップ 3 e: ビルドし、BizTalk Server ソリューションの配置
このトピックでは 2 つは展開お[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト (**BtsSalesforceIntegration**と**CustomPipeline**) を前の手順で作成しました。  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a>BizTalk Server プロジェクトをビルドして展開するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトをクリックして**プロパティ**です。  
  
2.  **展開** タブの**アプリケーション名**、入力**SalesforceIntegration**です。 **[保存]** をクリックします。  
  
3.  同様を右クリックし、 **CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトで、をクリックして**プロパティ**、し、[、**展開**] タブの**アプリケーション名前**プロパティ、入力**SalesforceIntegration**もう一度です。 **[保存]** をクリックします。 これにより、カスタム パイプライン コンポーネントと同じアプリケーションがデプロイされる、 **BtsSalesforceIntegration**プロジェクト。  
  
4.  ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**プロパティ**です。 [ソリューション プロパティ ページ] ダイアログ ボックスで、**構成プロパティ**、いることを確認し、**ビルド**と**展開**チェック ボックスがオンの両方**BtsSalesforceIntegration**と**CustomPipeline**プロジェクト。  
  
5.  ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**ソリューションのビルド**です。 ソリューションが正常にビルド、ソリューション名を再度右クリックし、クリックして**ソリューションの配置**です。 ソリューションが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールに展開されます。  
  
## <a name="see-also"></a>参照  
 [手順 3: Visual Studio での BizTalk Server ソリューションを作成します。](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)