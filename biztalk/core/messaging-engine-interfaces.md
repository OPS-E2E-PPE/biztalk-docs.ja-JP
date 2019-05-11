---
title: メッセージング エンジンのインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14241db3-edcf-4449-9ec8-2171a14496c0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08b8d795b6df72f3e555f527e3d995cab1d288e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394526"
---
# <a name="messaging-engine-interfaces"></a>メッセージング エンジンのインターフェイス
アダプターがメッセージング エンジンとの対話を許可するために使用できるパブリック インターフェイスが 3 つあります。 これらのインターフェイスについて、以下のセクションで説明します。  
  
## <a name="ibttransportproxy"></a>IBTTransportProxy  
 アダプターは常に、独自のトランスポート プロキシを使用してメッセージング エンジンと対話します。 トランスポート プロキシは、バッチの作成、メッセージ ファクトリの取得、エンジンへの分離受信者の登録などの処理に使用されます。  
  
## <a name="ibttransportbatch"></a>IBTTransportBatch  
 このインターフェイスは、メッセージング エンジンによって定義され、メッセージのバッチに対して処理を実行する際にアダプターが使用するメソッドを定義します。 メッセージング エンジンは、バッチを非同期に処理します。  
  
## <a name="ibtdtccommitconfirm"></a>IBTDTCCommitConfirm  
 バッチに対して明示的な Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションを使用するアダプターは、このインターフェイスを使用して、トランザクションの結果をエンジンに通知する必要があります。