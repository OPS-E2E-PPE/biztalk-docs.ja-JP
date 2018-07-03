---
title: BizTalk Server アプリケーションにおけるアイテム間の依存関係の追跡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 503cadfc-08e5-4b34-94a2-3b0ea6ad6228
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 491458e6c7b447e48b944537ec14184b452439db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012691"
---
# <a name="tracking-dependencies-between-artifacts-in-a-biztalk-server-application"></a>BizTalk Server アプリケーションにおけるアイテム間の依存関係の追跡
典型的な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションには、オーケストレーション、送信ポート、受信場所、パイプライン、スキーマ、マップなど、さまざまなアイテムが含まれています。 これらすべてのアイテムは、相互に依存しています。 次の表に、この依存関係を示します。  
  
|成果物|オーケストレーション|送信ポート|受信ポート|受信場所|パイプライン|マップ|スキーマ|  
|---------------|-------------------|---------------|------------------|----------------------|--------------|----------|-------------|  
|**オーケストレーション**||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||||  
|**送信ポート**|![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**受信ポート**|![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**受信場所**|||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|||  
|**パイプライン**||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||  
|**マップ**||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|  
|**[スキーマ]**||||||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||  
  
 この表が示すように、依存関係には 2 つのモードがあります。  
  
- 使用して (![を使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")) – アイテムが別のアイテムを使用して、送信ポートがパイプラインを使用してなど。  
  
- 使用して (![で使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")) – アイテムが別のアイテムによって使用される、たとえば、送信ポートがオーケストレーションによって使用されます。  
  
  アイテムを更新する必要がある場合、これらの依存関係を使用して、依存階層内の停止または再展開する必要があるアイテムを把握する必要があります。 この依存関係情報は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで利用できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]成果物は別のアイテムを使用しているかどうか管理コンソールに、両方のモードで依存関係情報が表示されます*だけでなく*成果物を別のアイテムによって使用するかどうか。  
  
## <a name="viewing-dependencies"></a>依存関係の表示  
 ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して依存関係を表示する方法について説明します。  
  
> [!NOTE]
>  次の手順は、オーケストレーションの依存関係を表示する方法を示しています。 同じ手順に従って他のアイテムの依存関係を表示することができます。  
  
#### <a name="to-view-dependencies-for-an-artifact"></a>アイテムの依存関係を表示するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールは、アプリケーションを展開し、クリックして**オーケストレーション**します。 中央のペインで、依存関係を表示しオーケストレーションを右クリックして**依存関係の表示**します。  
  
2. ウィンドウの下部、**依存関係の統計**ウィンドウで、2 つのカテゴリの依存関係を表示します。 **使用者**カテゴリは、特定のオーケストレーションを使用するアイテムを表示します。 **Using**カテゴリは、特定のオーケストレーションによって使用されている成果物を表示します。  
  
    ![オーケストレーションの依存関係](../core/media/dependency-orchestration.jpg "Dependency_Orchestration")  
  
    オーケストレーションに依存するその他の成果物がないため、**使用者**オーケストレーションの依存関係カテゴリは空です。 ただし、下、 **Using**オーケストレーションは 1 つの送信ポートに依存する依存関係モードでは、イメージを示しています。 依存関係の数はハイパーリンクとして表示されます。このハイパーリンクをクリックすると、オーケストレーションが依存する送信ポートだけが表示されます。 ハイパーリンクをクリックして送信ポートを一覧表示した後も、依存関係ウィンドウには送信ポートではなくオーケストレーションの依存関係の統計が表示されることに注意してください。  
  
    送信ポートを右クリックしてをクリックし、**依存関係の表示**ここでも、送信ポートの依存関係の一覧を表示します。 この依存関係ツリーは任意のレベルまで表示できます。 次の図に示すように、依存関係ツリー内の現在のレベルは、ウィンドウの上部にあるパンくずリストによって示されます。  
  
    ![依存関係ツリーの階層をパン](../core/media/dependency-breadcrumbs.jpg "Dependency_BreadCrumbs")