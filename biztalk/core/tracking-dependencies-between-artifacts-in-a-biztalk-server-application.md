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
ms.openlocfilehash: 1ba644a5a745b83c217d35b6697c2bf2c4444ca2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313818"
---
# <a name="tracking-dependencies-between-artifacts-in-a-biztalk-server-application"></a>BizTalk Server アプリケーションにおけるアイテム間の依存関係の追跡
一般的な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションは、オーケストレーションなどのさまざまな成果物、送信ポート、受信場所、パイプライン、スキーマ、マップ、および、いいねです。 これらすべてのアイテムでは、相互に依存関係があります。 次の表では、これらの依存関係を示します。  
  
|成果物|オーケストレーション|送信ポート|受信ポート|受信場所|パイプライン|マップ|スキーマ|  
|---------------|-------------------|---------------|------------------|----------------------|--------------|----------|-------------|  
|**オーケストレーション**||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||||  
|**送信ポート**|![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**受信ポート**|![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**受信場所**|||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|||  
|**パイプライン**||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||  
|**マップ**||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|  
|**[スキーマ]**||||||![使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||  
  
 表からわかるように、依存関係の 2 つのモードがあります。  
  
- 使用して (![を使用して](../core/media/dependency-using-icon.png "Dependency_Using_Icon")) – アイテムが別のアイテムを使用して、送信ポートがパイプラインを使用してなど。  
  
- 使用して (![で使用される](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")) – アイテムが別のアイテムによって使用される、たとえば、送信ポートがオーケストレーションによって使用されます。  
  
  これらの依存関係を持つ、アイテムを更新する必要がある場合おく必要があります、依存関係の階層でアイテムを停止または再展開する必要があります。 このような依存関係情報が表示されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]成果物は別のアイテムを使用しているかどうか管理コンソールに、両方のモードで依存関係情報が表示されます*だけでなく*成果物を別のアイテムによって使用するかどうか。  
  
## <a name="viewing-dependencies"></a>依存関係を表示  
 このセクションを使用して、依存関係を表示する方法に関する情報を提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
> [!NOTE]
>  次の手順は、オーケストレーションの依存関係を表示する方法について説明します。 他の成果物の依存関係を表示する同じ手順を行うことができます。  
  
#### <a name="to-view-dependencies-for-an-artifact"></a>成果物の依存関係を表示するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールは、アプリケーションを展開し、クリックして**オーケストレーション**します。 中央のペインで、依存関係を表示しオーケストレーションを右クリックして**依存関係の表示**します。  
  
2. ウィンドウの下部、**依存関係の統計**ウィンドウで、2 つのカテゴリの依存関係を表示します。 **使用者**カテゴリは、特定のオーケストレーションを使用するアイテムを表示します。 **Using**カテゴリは、特定のオーケストレーションによって使用されている成果物を表示します。  
  
    ![オーケストレーションの依存関係](../core/media/dependency-orchestration.jpg "Dependency_Orchestration")  
  
    オーケストレーションに依存するその他の成果物がないため、**使用者**オーケストレーションの依存関係カテゴリは空です。 ただし、下、 **Using**オーケストレーションは 1 つの送信ポートに依存する依存関係モードでは、イメージを示しています。 依存関係の数を表示すると、ハイパーリンクとしてクリックされると、オーケストレーションが依存している送信ポートのみが表示されます。 送信ポートを一覧表示するハイパーリンクをクリックした後も、依存関係ウィンドウも表示される、オーケストレーションと送信ポートではなく依存関係の統計に注意してください。  
  
    送信ポートを右クリックしてをクリックし、**依存関係の表示**ここでも、送信ポートの依存関係の一覧を表示します。 任意のレベルまで、このような依存関係ツリーを表示できます。 次の図に示すように、ウィンドウの上部にあるパンくずリストによって依存関係ツリーが位置するレベルが表示されます。  
  
    ![依存関係ツリーの階層をパン](../core/media/dependency-breadcrumbs.jpg "Dependency_BreadCrumbs")