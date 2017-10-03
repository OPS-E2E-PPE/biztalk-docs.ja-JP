---
title: "特別な操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: operations, special operations surfaced by the SAP adapter
ms.assetid: 8725fe63-6ff4-49c8-b386-d4c67e2be440
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2472d905e9e726b827d44da79bdfe840233354
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="special-operations"></a>特別な操作
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]いくつかの特別な操作を表示します。 これらの操作は、SAP システムの成果物に基づいていません。 アダプターのクライアント アプリケーションの機能を提供する表示されます。 特別な操作は次のとおりです。  
  
-   **RfcGetAttributes**です。 この操作は、RFC ノードの下に表示され、RFC SDK の機能を公開します。 RFC 接続に関する次の情報を提供します。  
  
    -   システム ID  
  
    -   パートナーのコード ページ  
  
    -   言語  
  
     詳細については、メッセージ スキーマを含む RfcGetAttributes 操作は、次を参照してください。 [RFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)です。  
  
-   **RfcConfirmTransID**です。 この操作は、TRFC ノードの下に表示され、RFC SDK の機能を公開します。 SAP システムでの SAP トランザクション Id を確認するのにには、この操作を使用します。  
  
     RfcConfirmTransID 操作を使用して、そのメッセージ スキーマについての説明を参照してください。 詳細について[SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。  
  
-   **文字列の SapAdapterUtilities.ConvertGuidToTid(Guid)**です。 これは、SAP アダプターのアセンブリによって公開されているパブリック メソッドです。 (はアダプターによって公開される操作)SAP トランザクション ID (TID) が指定された GUID にマップを返します。  
  
     内部的には、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] GUID に SAP システムに SAP トランザクション ID (TID) 作業 (LUW) の論理単位を識別するをマップします。 この GUID がクライアントに公開アダプター、tRFC (LUW) をコミットできるように、SAP システムでその TID を確認する RfcConfirmTransID 操作を呼び出すことによってです。  
  
     ただし、一部のシナリオについて、tRFC に関連付けられている TID を必要があります。 たとえば、問題のトラブルシューティングを SAP システムで LUW を識別することがあります。 このようなシナリオを呼び出せる**ConvertGuidToTid**です。 使用する**ConvertGuidToTid**コードで、プロジェクトに SAP アダプターのアセンブリへの参照を追加する必要があります。  
  
     TRFCs の呼び出しの詳細については、次を参照してください。 [SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。 次の例を呼び出す方法を示しています。 **ConvertGuidToTid**です。  
  
    ```  
    // messageGuid is the GUID associated with a tRFC or IDOC  
  
    string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
    ```  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)