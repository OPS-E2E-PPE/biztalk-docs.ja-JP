---
title: "SAP Rfc に対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd4ebbb33e9f9791589a3ef271412c8ae20090f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-rfcs-in-sap"></a>SAP Rfc に対する操作
使用することができます、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] RFC クライアントと RFC サーバーの両方です。 RFC クライアントのシナリオで、アプリケーションを呼び出す Rfc SAP システムでの RFC 操作を呼び出すことによって、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 SAP RFC のサーバーのシナリオで、上、システムでの Rfc が呼び出される、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を呼び出す、RFC として、アプリケーションでの操作です。  
  
## <a name="rfc-operations"></a>RFC 操作  
 Rfc は、名前で、RFC のメタデータ カテゴリ ノードで [操作] として表示された、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 (参照したり、Rfc の検索、 **RFC**ノードを使用するときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を SAP システムからメタデータを取得できる Rfc のみを表示することができます。 アダプターでは、RFC SDK を使用して、RFC SDK によってサポートされていないデータ型のパラメーターが含まれている Rfc を提示できないために、このメタデータを取得します。 たとえば、アダプターは、Rfc ITAB II 型の構造体またはテーブルを含むを画面ことはできません。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Rfc で、次をサポートしています。  
  
-   インポートのパラメーター  
  
-   パラメーターをエクスポートします。  
  
-   変化させるパラメーター  
  
 メッセージの構造と、アダプターによって Rfc に使用される SOAP アクションの詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)です。  
  
## <a name="invoking-rfcs-on-an-sap-system"></a>SAP システムでの Rfc を呼び出す  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムに対して、RFC の名前を実行する個々 の操作として Rfc を表示します。 SAP システムで RFC を呼び出すには、するには、アダプターで適切に名前付きの RFC 操作を呼び出します。  
  
 詳細については。  
  
-   BizTalk Server を使用して RFC 呼び出しを参照してください[を使用して BizTalk Server が呼び出す Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)です。  
  
-   WCF サービス モデルを使用して RFC 呼び出しを参照してください[WCF サービス モデルを使用して SAP で呼び出す Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)です。  
  
-   WCF チャネル モデルを使用して RFC 呼び出しを参照してください[WCF チャネル モデルを使用して SAP システムに対して操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)です。  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a>SAP システムから受信側の受信 RFC 呼び出し  
 Sap クライアントとして動作し、外部の RFC サーバー上の関数モジュールを起動することができます。 この機能が有効にします。  
  
-   継続的にポーリングする SAP 通知の Rfc を呼び出すことによって、外部のシステムなしに外部システムに通知をプッシュする SAP です。  
  
-   SAP システムの外部のビジネス ロジックの実装です。 SAP システムは、RFC サーバーで、外部プログラムを呼び出すことができます。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムからこのような受信 RFC 呼び出しを受信する RFC サーバーとして機能できます。 SAP からアダプターが RFC 呼び出しを受け取ると、アプリケーションでその RFC 操作を呼び出します。  
  
 RFC サーバーとして実行するようにアダプター。  
  
-   RFC は、SAP システムで宣言する必要があります。 これは、アダプターは、SAP システムの RFC を説明するメタデータを取得できるようにします。 RFC は、実際には、アプリケーションで実装されます。  
  
-   アダプターは、SAP ゲートウェイで、RFC 変換先を登録する必要があります。 登録は、プログラム ID と呼ばれる論理名をに基づいてください。 プログラム ID、SAP ゲートウェイを指定し、この登録用のサーバーの SAP への URI の接続でパラメーターを指定するとします。  
  
 次の例では、プログラム ID、MYDEST を通じて RFC 呼び出しに必要な ABAP コードを示します。  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 詳細については。  
  
-   BizTalk Server を使用して、RFC サーバー呼び出しの受信を参照してください[受信 RFC の呼び出しを使用して BizTalk Server で受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)です。  
  
-   モデルを使用して、WCF サービス、RFC サーバー呼び出しの受信を参照してください[WCF サービス モデルを使用して SAP で受信 RFC 呼び出しの受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)です。  
  
-   WCF チャネル モデルを使用して、RFC サーバー呼び出しの受信を参照してください[WCF チャネル モデルを使用して SAP システムからの受信操作の受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)です。  
  
## <a name="special-rfc-operations"></a>特殊な RFC 操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで特別な特定 RFC 操作も実行できます。 このような 1 つの操作は、RfcGetAttributes です。  
  
-   **RfcGetAttributes**です。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]この操作を使用して、システム ID、パートナーのコード ページ、および言語など、RFC 接続のパラメーターに関する情報を取得します。 この操作で使用可能な**RFC**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
 メッセージの構造と SAP システムで RfcGetAttributes 操作の呼び出しの SOAP アクションの詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)