---
title: SAP アダプターを物理ポートのバインドを手動で構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, sending messages to the SAP system
- physical port binding, manually configuring
- deploying, receiving messages from the SAP system
ms.assetid: c4f547aa-5514-4ca9-809b-d8d395de419c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14aea45a1032a2e01e9560d9ab47e85e75506836
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994611"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sap-adapter"></a>SAP アダプターを物理ポートのバインドを手動で構成します。
構成、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]を使用して WCF カスタム バインドとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 

## <a name="port-overview"></a>ポートの概要
アダプタの展開後にすることを使用しての SAP システムからメッセージを送受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アダプターを展開する手順は、に応じて異なります。  
  
- 間の通信の方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 送信、受信を構成することができます送信と受信、または受信送信ポート。 選択項目は次のとおりです。  
  
  |ポートの方向|通信方式|選択する通信の方向|  
  |---|---|---|  
  |Send|一方向|常にこのポートでメッセージを送信します。|  
  |Receive|一方向|常にこのポートでメッセージを受信します。|  
  |送信 - 受信|要求 - 応答|要求の送信と応答の受信をされます。|  
  |受信 - 送信|送信請求 - 応答送信アダプター|要求の受信と応答の送信を行います。|  
  
   詳細については、次を参照してください。[送信ポートを作成](../../core/how-to-create-a-send-port2.md)、または[受信ポートを作成](../../core/how-to-create-a-receive-port.md)です。
  
- かどうか、アダプターは、SAP システムにメッセージを送信または SAP システムからメッセージを受信します。 によって送信またはメッセージを受信するかどうかを作成、送信または受信ポートします。  
  
  > [!NOTE]
  >  構成、送信またはによって作成されるバインド構成ファイルをインポートしてポートを受信することができますも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。 このバインド ファイルを使用してポートを構成する方法の詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)します。
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Wcf-custom アダプターと Oracle データベース アダプターを使用してポートを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter.md)  
  
-   [WCF-SAP アダプターを使用してポートを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-port-using-the-wcf-sap-adapter.md)  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを作成するための構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)