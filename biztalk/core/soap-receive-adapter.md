---
title: SOAP 受信アダプター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, receive adapters
- receive adapters, SOAP adapters
ms.assetid: bb968fa8-0515-4f3a-bb39-9effb83e960c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fac19580d6083ed1b0d4be315d3285acf14fcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278394"
---
# <a name="soap-receive-adapter"></a>SOAP 受信アダプター
SOAP 受信アダプターは、Web サービス要求を受信するために使用します。 BizTalk メッセージ オブジェクトの作成、および関連するプロパティのメッセージ コンテキストへの昇格を行います。  
  
 SOAP 受信アダプター URI は、1 つまたは複数の BizTalk オーケストレーションに関連付ける必要がありますまたはスキーマを持つ web サービスとして公開されている、 **BizTalk Web サービス公開ウィザード**です。 公開された Web サービスは、BizTalk アセンブリ内の 1 つ以上の BizTalk Server オーケストレーションまたはスキーマと関連付けられている 1 つ以上の Web メソッドを公開します。 事実上、公開された Web サービスは、BizTalk オーケストレーションまたはスキーマのサーバー プロキシとして機能し、クライアントと BizTalk オーケストレーションまたはスキーマの間で要求と応答を転送します。 BizTalk オーケストレーションまたはスキーマを web サービスとして公開の詳細については、次を参照してください。 [Web サービスの公開](../core/publishing-web-services.md)です。  
  
 SOAP アダプターを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。 SOAP アダプターを使用するように一方向の受信場所を構成した場合、関連する Web サービスによって受信ポートにバインドされた BizTalk アセンブリが呼び出され、クライアントに要求の状態が返されます。 SOAP アダプターを使用するように要求 - 応答 (双方向) の受信場所を構成した場合、関連する Web サービスによって受信ポートにバインドされた BizTalk アセンブリが呼び出され、クライアントに応答ドキュメントが返されます。 要求-応答メッセージングの詳細については、次を参照してください。[要求-応答のメッセージング](../core/request-response-messaging.md)です。  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターとは何ですか。](../core/what-is-the-soap-adapter.md)   
 [SOAP アダプタのセキュリティに関する推奨事項](../core/soap-adapter-security-recommendations.md)