---
title: 手順 3 e:ビルドし、BizTalk Server ソリューションの配置 |Microsoft Docs
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
ms.openlocfilehash: 0ab07af6e0937ff015acc4acdd4e0ad116ea72a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392591"
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a>手順 3 e:BizTalk Server ソリューション ビルドしてデプロイ
このトピックでは、2 つをデプロイする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト (**BtsSalesforceIntegration**と**CustomPipeline**)、前の手順で作成しました。  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a>構築および BizTalk Server プロジェクトをデプロイするには  
  
1. ソリューション エクスプ ローラーで右クリックし、 **BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトをクリックして**プロパティ**します。  
  
2. **展開** タブの**アプリケーション名**、入力**SalesforceIntegration**します。 **[保存]** をクリックします。  
  
3. 同様に、右クリックし、 **CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトで、をクリックして**プロパティ**、し、**展開** タブの**アプリケーション名前**プロパティ、入力**SalesforceIntegration**もう一度です。 **[保存]** をクリックします。 これにより、カスタム パイプライン コンポーネントが同じアプリケーションとしてデプロイされる、 **BtsSalesforceIntegration**プロジェクト。  
  
4. ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**プロパティ**します。 [ソリューション プロパティ ページ] ダイアログ ボックスで、**構成プロパティ**、ことを確認します、**ビルド**と**デプロイ**チェック ボックスがオンの両方**BtsSalesforceIntegration**と**CustomPipeline**プロジェクト。  
  
5. ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックし、**ソリューションのビルド**します。 ソリューション名を右クリックし、もう一度、ソリューションが正常にビルド、クリックして**ソリューションの配置**します。 ソリューションをデプロイ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:Visual Studio で BizTalk Server ソリューションを作成します。](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)