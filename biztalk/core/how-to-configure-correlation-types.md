---
title: "関連付けの種類を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 646ac7dafd5207a2558e45252077efe2d9616a70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-correlation-types"></a>関連付けの種類を構成する方法
使用する、**関連付けのプロパティ** ダイアログ ボックスを追加または関連付けの種類からプロパティを削除します。 関連付けの種類は、関連付けセットのプロパティの一覧であり、実行時に送受信の動作によって使用されて、オーケストレーションの正しいインスタンスに受信メッセージが適切に関連付けられるようにします。  
  
 ダイアログ ボックスにはペインが 2 つあり、それぞれにプロパティの一覧が含まれています。 左ペインの "利用可能なプロパティ" には、プロジェクト内で定義または参照されているプロパティのすべてが、ツリー ビューで表示されます。 既定で表示されるプロパティは、BizTalk Server で定義されているシステム プロパティですが、プロパティ スキーマで独自のプロパティを定義することもできます。 プロパティ スキーマの作成の詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)です。  
  
> [!NOTE]
>  スキーマのプロパティは、関連付けの種類で使用する前に昇格させる必要があります。 詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)です。  
  
### <a name="to-add-and-configure-a-correlation-type"></a>関連付けの種類を追加および構成するには  
  
-   オーケストレーションの種類 ウィンドウで、右クリック**関連付けの種類** をクリックし、**新しい関連付けの種類**です。  
  
     **関連付けのプロパティ** ダイアログ ボックスが表示されたらです。 関連付けの種類に含めるプロパティを追加します。  
  
    > [!NOTE]
    >  アクセスする場合、**関連付けのプロパティ** ダイアログ ボックスを直接相関関係の設定が既に存在しない場合、関連付けセットの関連付けの種類が作成されます。 加えた変更は、新しい関連付けの種類に保存され、関連付けセットは、新しい関連付けの種類を使用するよう構成されます。 関連付けセットに関連付けの種類が既にあった場合、変更を加えると、その関連付けの種類が変更されます。  
  
### <a name="to-remove-a-correlation-type"></a>関連付けの種類を削除するには  
  
-   オーケストレーションの種類 ウィンドウで、をクリックして削除する関連付けの種類を右クリックして**削除**です。