---
title: Wcf-customisolated アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-CustomIsolated adapters, about WCF-CustomIsolated adapters
ms.assetid: 872fe97a-8a96-4b2a-8cc1-2db9b315c44f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b60cc39092961703f45921c34a518f3da89691c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242793"
---
# <a name="what-is-the-wcf-customisolated-adapter"></a>Wcf-customisolated アダプターとは何ですか。
Wcf-customisolated アダプターは、分離ホストで BizTalk Server で WCF 拡張機能コンポーネントの使用できるように使用されます。 アダプターは、WCF フレームワークの完全な柔軟性を使用します。 ユーザーを選択し、受信場所の WCF バインドを構成し、エンドポイントの動作とセキュリティ設定を指定できます。 このアダプターは、インターネット インフォメーション サービス (IIS) でホストされているトランスポートでのみ使用できます。  
  
 Wcf-customisolated アダプタは、受信アダプタのみで構成されます。 受信場所の WCF バインド、サービス動作、エンドポイントの動作、セキュリティ メカニズム、および選択および構成する受信メッセージ本文のソースから Wcf-customisolated 受信アダプターは WCF サービス要求の受信を使用します。分離ホストで実行されています。 Wcf-customisolated 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。  
  
 WCF の詳細については、受信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>参照  
 [Wcf-customisolated アダプターを構成します。](../core/configuring-the-wcf-customisolated-adapter.md)   
 [WCF アダプター](../core/wcf-adapters.md)