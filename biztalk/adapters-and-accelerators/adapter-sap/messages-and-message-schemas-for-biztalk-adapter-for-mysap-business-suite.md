---
title: "メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマを |Microsoft ドキュメント"
description: "BizTalk Server 用 mySAP アダプターによって使用されるメッセージとデータ型の XML 構造"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75ea5c27-8297-47bf-bcfd-503870349189
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9db6ec6b0fbea7ce5c8f90158126d52cbc7530ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite"></a>メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ

## <a name="overview"></a>概要
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 これは、アプリケーションがそれで呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。 これらの操作がチャネル経由で SOAP メッセージを送信することによって呼び出されます。 応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。  
  
 として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]標準を使用してその操作とデータ型のメタデータが公開[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズムです。 このトピックのセクションでは、メッセージの XML 構造の記述し、データの種類を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [基本的な SAP データ型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)  
  
-   [カスタム Rfc のデータ型マッピング](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)  
  
-   [IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)  
  
-   [Idoc を受信するためのメッセージ コンテキスト プロパティ](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)  
  
-   [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)  
  
-   [TRFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)  
  
-   [BAPI 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)  
  
-   [特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)  
  
-   [メッセージ バージョン管理のサポート](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)  
  
