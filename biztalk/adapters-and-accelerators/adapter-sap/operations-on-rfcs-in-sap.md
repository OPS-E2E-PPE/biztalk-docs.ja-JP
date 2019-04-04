---
title: SAP で Rfc に対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, operations on RFCs
- adapters, operations on IDOCs
- RFC, receiving inbound RFC calls from an SAP system
- RFCs, invoking RFCs on an SAP system
- adapters, operations on BAPIs
- RFC client
- adapters, operations on tRFCs
- RFC server
ms.assetid: ca1b7b00-a9cf-41bc-b87c-2e7ce8cff65c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8219a063fed2c940cfcd2658937fde0686542d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015361"
---
# <a name="operations-on-rfcs-in-sap"></a>SAP で Rfc に対する操作
使用することができます、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]クライアントが RFC と RFC サーバーの両方。 RFC クライアントのシナリオで、アプリケーションが呼び出す Rfc SAP システムでの RFC 操作を呼び出すことによって、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 システム、SAP の RFC サーバー シナリオでの Rfc を呼び出される、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]をさらに、アプリケーションに対する操作として、RFC を呼び出します。  
  
## <a name="rfc-operations"></a>RFC 操作  
 Rfc は、名前で、RFC のメタデータ カテゴリ ノードの下での操作として表示されます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 (参照したり、Rfc の検索、 **RFC**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を SAP システムからメタデータを取得できる Rfc のみを表示することができます。 アダプターでは、RFC SDK を使用して、RFC SDK でサポートされていないデータ型を持つパラメーターを含む Rfc を surface ことはできませんので、このメタデータを取得します。 たとえば、アダプターでは、Rfc ITAB II 型の構造体またはテーブルが含まれているを画面ことはできません。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Rfc に対する次のサポートします。  
  
- インポート パラメーター  
  
- パラメーターをエクスポートします。  
  
- 変化するパラメーター  
  
  メッセージの構造と、アダプターによって Rfc に使用される SOAP アクションの詳細については、[RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)を参照してください。  
  
## <a name="invoking-rfcs-on-an-sap-system"></a>SAP システムでの Rfc を呼び出す  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで、RFC の名前を取得する個々 の操作として Rfc 明らかになります。 SAP システムの RFC を呼び出すには、するには、アダプターで適切に名前付きの RFC 操作を呼び出します。  
  
 詳細については。  
  
-   BizTalk Server を使用して、RFC の呼び出しを参照してください[を使用して BizTalk Server が呼び出す Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)します。  
  
-   WCF サービス モデルを使用して、RFC の呼び出しを参照してください[WCF サービス モデルを使用して SAP で Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)します。  
  
-   WCF チャネル モデルを使用して、RFC の呼び出しを参照してください[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)します。  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a>SAP システムからの受信側の受信 RFC 呼び出し  
 For SAP をクライアントとして動作させ、外部の RFC サーバー上のモジュールの関数を呼び出すことができます。 この機能が有効にします。  
  
- 外部のシステム通知の Rfc を呼び出すことで SAP を継続的にポーリングする必要はなく、外部システムにプッシュ通知を SAP します。  
  
- SAP システムの外部のビジネス ロジックの実装です。 SAP システムは、RFC サーバーで、外部プログラムを呼び出すことができます。  
  
  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムからこのような受信 RFC 呼び出しを受信する RFC サーバーとして機能できます。 Sap で RFC 呼び出しを受信すると、アプリケーションでは、その RFC 操作を呼び出します。  
  
  アダプターが RFC サーバーとして実行するには。  
  
- SAP システムでは、RFC を宣言する必要があります。 これはので、アダプターは、SAP システムから RFC を記述するメタデータを取得できます。 RFC は、アプリケーションで実際に実装されます。  
  
- アダプターは、SAP ゲートウェイ RFC 転送先に登録する必要があります。 登録は、プログラム ID と呼ばれる論理名をに基づいてください。 接続を SAP ゲートウェイ、プログラム ID を指定し、この登録用のサーバー、SAP の URI でパラメーターを指定します。  
  
  次の例では、プログラム ID、MYDEST を通じて RFC の呼び出しに必要な ABAP コードを示します。  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 詳細については。  
  
-   BizTalk Server を使用して RFC サーバー呼び出しの受信を参照してください[受信 RFC の呼び出しを使用して BizTalk Server で受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)します。  
  
-   WCF サービス モデルを使用して RFC サーバー呼び出しの受信を参照してください[WCF サービス モデルを使用して SAP で受信 RFC 呼び出しの受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)します。  
  
-   WCF チャネル モデルを使用して RFC サーバー呼び出しの受信を参照してください[WCF チャネル モデルを使用して、SAP システムからの受信操作の受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)します。  
  
## <a name="special-rfc-operations"></a>RFC の特別な操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで特定の特別な RFC 操作も実行できます。 このような 1 つの操作では、RfcGetAttributes です。  
  
- **RfcGetAttributes**します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]この操作を使用して、システム ID、パートナーのコード ページ、および言語などの RFC 接続パラメーターに関する情報を取得します。 この操作で使用可能な**RFC**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
  メッセージの構造と SAP システムで RfcGetAttributes 操作を呼び出すための SOAP アクションの詳細については、[RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)