---
title: BizTalk Server アプリケーション内のアイテム間の依存関係の追跡 |Microsoft ドキュメント
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
ms.openlocfilehash: 3edd162075f1ad660c005fd387ac9bc6c8c79e38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279954"
---
# <a name="tracking-dependencies-between-artifacts-in-a-biztalk-server-application"></a>BizTalk Server アプリケーションにおけるアイテム間の依存関係の追跡
典型的な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションには、オーケストレーション、送信ポート、受信場所、パイプライン、スキーマ、マップなど、さまざまなアイテムが含まれています。 これらすべてのアイテムは、相互に依存しています。 次の表に、この依存関係を示します。  
  
|成果物|オーケストレーション|送信ポート|受信ポート|受信場所|パイプライン|マップ|スキーマ|  
|---------------|-------------------|---------------|------------------|----------------------|--------------|----------|-------------|  
|**オーケストレーション**||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||||  
|**送信ポート**|![によって使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**受信ポート**|![によって使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**受信場所**|||![によって使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|||  
|**パイプライン**||![によって使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![によって使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||  
|**マップ**||![によって使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|![によって使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|  
|**スキーマ**||||||![によって使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||  
  
 この表が示すように、依存関係には 2 つのモードがあります。  
  
-   使用して (![Using](../core/media/dependency-using-icon.png "Dependency_Using_Icon")) –、成果物は、別のアイテムを使用して、たとえば、送信ポートはパイプラインを使用します。  
  
-   使用して (![によって使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")) – アイテムが別のアイテムによって使用される、たとえば、送信ポートがオーケストレーションによって使用されます。  
  
 アイテムを更新する必要がある場合、これらの依存関係を使用して、依存階層内の停止または再展開する必要があるアイテムを把握する必要があります。 この依存関係情報は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで利用できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、成果物は、別のアイテムを使用しているかどうか – 両方のモードで依存関係情報を表示*だけでなく*成果物が別のアイテムによって使用されるかどうか。  
  
## <a name="viewing-dependencies"></a>依存関係の表示  
 ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して依存関係を表示する方法について説明します。  
  
> [!NOTE]
>  次の手順は、オーケストレーションの依存関係を表示する方法を示しています。 同じ手順に従って他のアイテムの依存関係を表示することができます。  
  
#### <a name="to-view-dependencies-for-an-artifact"></a>アイテムの依存関係を表示するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、アプリケーションを展開し、をクリックして**オーケストレーション**です。 中央のペインで、依存関係を表示しオーケストレーションを右クリックして**ビューの依存関係**です。  
  
2.  下部のウィンドウの**依存関係の統計** ウィンドウで、次の 2 つのカテゴリの依存関係が表示されます。 **によって使用される**カテゴリは、特定のオーケストレーションを使用している成果物を表示します。 **Using**カテゴリは、特定のオーケストレーションによって使用されている成果物を表示します。  
  
     ![オーケストレーションの依存関係](../core/media/dependency-orchestration.jpg "Dependency_Orchestration")  
  
     その他の成果物が、オーケストレーションに依存しないため、**によって使用される**オーケストレーションの依存関係カテゴリは空です。 ただし、下、**を使用する**オーケストレーション、1 つの送信ポートに依存している依存関係モードでは、イメージを示しています。 依存関係の数はハイパーリンクとして表示されます。このハイパーリンクをクリックすると、オーケストレーションが依存する送信ポートだけが表示されます。 ハイパーリンクをクリックして送信ポートを一覧表示した後も、依存関係ウィンドウには送信ポートではなくオーケストレーションの依存関係の統計が表示されることに注意してください。  
  
     送信ポートを右クリックし、をクリックすることができます**ビューの依存関係**もう一度、送信ポートの依存関係の一覧を表示します。 この依存関係ツリーは任意のレベルまで表示できます。 次の図に示すように、依存関係ツリー内の現在のレベルは、ウィンドウの上部にあるパンくずリストによって示されます。  
  
     ![階層リンクの依存関係ツリーの bread](../core/media/dependency-breadcrumbs.jpg "Dependency_BreadCrumbs")