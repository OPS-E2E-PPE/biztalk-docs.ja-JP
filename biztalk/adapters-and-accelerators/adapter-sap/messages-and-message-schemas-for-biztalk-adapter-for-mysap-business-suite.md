---
title: メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ |Microsoft Docs
description: BizTalk Server 用 mySAP アダプターによって使用されるメッセージとデータの種類の XML 構造
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ea5c27-8297-47bf-bcfd-503870349189
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 119fe8aea98266e0fcd3b26bff439b6136b3b755
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373220"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite"></a>メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ

## <a name="overview"></a>概要
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 アプリケーションがそれを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。 これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。 応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。  
  
 として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]標準を使用して、その操作とデータ型のメタデータを公開する[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズム。 このトピックのセクションでは、メッセージの XML 構造を記述して、データの種類を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP の基本的なデータ型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)  
  
-   [カスタム RFC のデータ型のマッピング](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)  
  
-   [IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)  
  
-   [IDOC を受信するためのメッセージ コンテキストのプロパティ](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)  
  
-   [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)  
  
-   [tRFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)  
  
-   [BAPI 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)  
  
-   [特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)  
  
-   [メッセージ バージョン管理のサポート](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)  
  
