---
title: 特別な操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, special operations surfaced by the SAP adapter
ms.assetid: 8725fe63-6ff4-49c8-b386-d4c67e2be440
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bada45064e588748b25947e08b104dc79838ee0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975987"
---
# <a name="special-operations"></a>特別な操作
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスのいくつかの特別な操作です。 これらの操作は、SAP システムの成果物には基づいていません。 アダプターのクライアント アプリケーションの機能を提供するは表示されます。 特別な操作は次のとおりです。  
  
- **RfcGetAttributes**します。 この操作は、RFC ノードの下に表示され、RFC SDK の機能を公開します。 RFC 接続に関する次の情報が提供します。  
  
  - システム ID  
  
  - パートナーのコード ページ  
  
  - 言語  
  
    そのメッセージのスキーマを含む RfcGetAttributes 操作に関する詳細については、[RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)を参照してください。  
  
- **RfcConfirmTransID**します。 この操作は、TRFC ノードの下に表示され、RFC SDK の機能を公開します。 SAP システムでの SAP トランザクション Id を確認するのにには、この操作を使用します。  
  
   RfcConfirmTransID 操作を使用して、そのメッセージ スキーマの詳細についてを参照してください。 詳細について[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。  
  
- **文字列の SapAdapterUtilities.ConvertGuidToTid(Guid)** します。 これは、SAP アダプターのアセンブリによって公開されるパブリック メソッドです。 (その操作がないアダプターします。)指定された GUID にマップされている ID (TID) SAP トランザクションを返します。  
  
   内部的には、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] GUID に SAP システムに関する SAP トランザクション ID (TID) 作業 (LUW) の論理単位を識別するをマップします。 この GUID がクライアントに公開アダプター、tRFC (LUW) をコミットできるように、SAP システムでは、その TID を確認する RfcConfirmTransID 操作を呼び出すことによって。  
  
   ただし、一部のシナリオに関連付けられた、tRFC TID を必要があります。 たとえば、特定の問題をトラブルシューティングする SAP システムで LUW たい場合があります。 このようなシナリオを呼び出すことができます**ConvertGuidToTid**します。 使用する**ConvertGuidToTid**コードをプロジェクトに SAP アダプターのアセンブリへの参照を追加する必要があります。  
  
   Trfc を呼び出す方法の詳細については、[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)を参照してください。 次の例を呼び出す方法を示しています。 **ConvertGuidToTid**します。  
  
  ```  
  // messageGuid is the GUID associated with a tRFC or IDOC  
  
  string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
  ```  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)