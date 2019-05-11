---
title: 関連付けの種類を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69770055b1d373b355bfd853e26bf463aab1858d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341494"
---
# <a name="how-to-configure-correlation-types"></a>関連付けの種類を構成する方法
使用する、**関連付けのプロパティ** ダイアログ ボックスを追加または関連付けの種類からのプロパティを削除します。 関連付けの種類には、送信でが使用され、実行時にオーケストレーションの適切なインスタンスで、受信メッセージが正しく関連付けられないことを確認するアクティビティを受信する、関連付けセットのプロパティが一覧表示します。  
  
 プロパティの一覧を格納している各ダイアログ ボックスには、2 つのペインがあります。 左側のウィンドウでは、「使用可能なプロパティ」には、すべてのプロパティは、プロジェクトで定義されているまたはその参照先のツリー ビューが含まれています。 既定で表示されるプロパティは、BizTalk Server で定義されている、システム プロパティがプロパティ スキーマで、独自のプロパティを定義することもできます。 プロパティ スキーマの作成の詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)します。  
  
> [!NOTE]
>  関連付けの種類で使用するに、スキーマのプロパティを昇格する必要があります。 詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)します。  
  
### <a name="to-add-and-configure-a-correlation-type"></a>追加して、関連付けの種類を構成するには  
  
-   オーケストレーションの種類 ウィンドウで、右クリック**関連付けの種類**し**新しい関連付けの種類**します。  
  
     **関連付けのプロパティ** ダイアログ ボックスが表示されます。 関連付けの種類で追加するプロパティを追加します。  
  
    > [!NOTE]
    >  アクセスする場合、**関連付けのプロパティ**ダイアログ ボックスで直接関連付けセットが既に存在しない場合、関連付けセットの関連付けの種類が作成されます。 新しい関連付けの種類に変更が保存され、関連付けセットは、新しい関連付けの種類を使用するように構成されます。 関連付けセットの関連付けの種類が既に存在して、変更を加えた場合は、関連付けの種類が変更されます。  
  
### <a name="to-remove-a-correlation-type"></a>関連付けの種類を削除するには  
  
-   オーケストレーションの種類 ウィンドウで、クリックして削除する関連付けの種類を右クリックして**削除**します。