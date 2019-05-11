---
title: SOAP 受信アダプター |Microsoft Docs
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
ms.openlocfilehash: 908554ad129fed6c99f4b8bb7e1b197cb4bc0ca6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244438"
---
# <a name="soap-receive-adapter"></a>SOAP 受信アダプター
SOAP を使用する受信アダプタ Web サービス要求を受信します。 SOAP 受信アダプターは、BizTalk メッセージ オブジェクトを作成し、メッセージ コンテキストに関連付けられているプロパティを昇格させます。  
  
 SOAP 受信アダプター URI は、1 つまたは複数の BizTalk オーケストレーションに関連付ける必要がありますまたはスキーマを持つ web サービスとして公開されている、 **BizTalk Web サービス公開ウィザード**します。 公開済み web サービスは、BizTalk Server オーケストレーションまたはスキーマを BizTalk アセンブリ内の 1 つまたは複数と関連付けられている 1 つまたは複数の web メソッドを公開します。 実際には、公開された web サービスは、BizTalk オーケストレーションまたはスキーマと転送の要求と、クライアントと、BizTalk オーケストレーションまたはスキーマの間の応答、サーバーのプロキシとして機能します。 BizTalk オーケストレーションまたはスキーマを web サービスとしての発行の詳細については、次を参照してください。 [Web サービスの公開](../core/publishing-web-services.md)します。  
  
 SOAP アダプタを使用する受信場所は、一方向として構成するか、要求-応答 (双方向)。 一方向の受信場所を構成するには、SOAP アダプターを使用すると関連付けられている web サービス、受信ポートにバインドされた BizTalk アセンブリを呼び出すクライアントに要求の状態を返します。 要求応答 (双方向) の受信場所を構成するには、SOAP アダプターを使用すると関連付けられている web サービス、受信ポートにバインドされた BizTalk アセンブリを呼び出すクライアントに応答ドキュメントを返します。 要求-応答メッセージングの詳細については、次を参照してください。[要求-応答メッセージング](../core/request-response-messaging.md)します。  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターとは何ですか。](../core/what-is-the-soap-adapter.md)   
 [SOAP アダプターのセキュリティに関する推奨事項](../core/soap-adapter-security-recommendations.md)