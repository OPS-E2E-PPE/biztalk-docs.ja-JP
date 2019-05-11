---
title: Wcf-custom アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom adapters, about WCF-Custom adapters
ms.assetid: 7b2178dd-f737-4784-9bcb-e2b3979bfb0d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eba1882957ed6974420d4827a43f90e1ef7ecba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242760"
---
# <a name="what-is-the-wcf-custom-adapter"></a>Wcf-custom アダプターとは何ですか。
Wcf-custom アダプターは BizTalk Server で WCF 拡張機能コンポーネントの使用を有効にするために使用します。 アダプターは、WCF フレームワークの完全な柔軟性を使用します。 受信場所の WCF バインドを構成および送信ポートを選択することができます。 また、エンドポイント動作やセキュリティ設定を設定することもできます。  
  
 Wcf-custom アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。  
  
 **Wcf-custom 受信アダプター**  
  
 WCF カスタムを使用する受信アダプターは、バインド、サービス動作、エンドポイントの動作、セキュリティ メカニズムを介して WCF サービス要求を受信して、本文の受信メッセージのソースを選択して、トランスポート プロパティ ダイアログで構成します。受信場所。 Wcf-custom 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。  
  
 **Wcf-custom 送信アダプタ**  
  
 Wcf-custom 送信アダプターを使用して、バインド、サービス動作、エンドポイントの動作、セキュリティ メカニズム、および選択および構成する送信メッセージの本文のソースを型宣言不要なコントラクトを介して WCF サービスを呼び出します。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。  
  
## <a name="see-also"></a>参照  
 [Wcf-custom アダプターを構成します。](../core/configuring-the-wcf-custom-adapter.md)   
 [WCF アダプター](../core/wcf-adapters.md)