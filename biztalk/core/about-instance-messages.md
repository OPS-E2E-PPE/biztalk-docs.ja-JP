---
title: "インスタンス メッセージについて |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de7fc3d3-57a7-4df9-b981-127e21941e22
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf956fb9f201697ac8c2b7da2135e469e03de55e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-instance-messages"></a>インスタンス メッセージについて
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、インスタンス メッセージの送受信を行います。通常、各インスタンス メッセージは、注文書などの 1 つ以上のビジネス ドキュメントを表します。 インスタンス メッセージは、1 つ以上のスキーマで定義されるメッセージ構造のインスタンスです。 スキーマまたはスキーマ セットは、有効なインスタンス メッセージを構成するための情報を定義します。 たとえば、注文書を定義して、複数のレコード (ShipTo レコード、BillTo レコード、Item レコードなど) を格納することがあります。 これらの各レコードを定義して、固有のサブレコードやフィールドを格納できます。 対応するスキーマでは、これらのレコードやフィールドに関する情報を定義します。また、対応するインスタンス メッセージは、スキーマに基づいて構成された注文書のデータを含む実際の注文書を格納します。  
  
 BizTalk Server は、拡張可能なさまざまな形式でインスタンス メッセージの送受信を行うことができます。特に XML 形式は重要な形式です。すべてのメッセージ形式は、内部処理によって XML 形式に変換されます。 XML ドキュメントでは、階層的に配置されている開始タグや終了タグに関する定義のセットを使用して、メッセージ内のデータの編成、およびデータ項目の終了場所と別のデータ項目の開始場所を判別します。 インスタンス メッセージに対応する XML スキーマでは、あるタグ内で使用可能なタグとその順序を定義します。これにより、メッセージの構造が管理されます。  
  
 フラット ファイル形式という種類の形式は、レガシ システムで一般的に使用されます。 この形式では、タブなどの区切り記号と固定長のフィールドを組み合わせて、データ項目の終了場所と別のデータ項目の開始場所を設定します。  
  
 このセクションでは、BizTalk Server で一般的に処理されるこれらの 2 種類のメッセージの構造の概要について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML メッセージの構造](../core/structure-of-an-xml-message.md)  
  
-   [フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md)