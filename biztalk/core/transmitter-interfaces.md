---
title: 送信元インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffa6db3b-739e-438c-b410-8823a20eed82
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e922cd2526002306928b2eae3418185986ed741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279722"
---
# <a name="transmitter-interfaces"></a>送信元インターフェイス
必須のアダプター インターフェイスに加えて (送信) アダプターの送信、どちらかを実装する必要があります**IBTTransmitter**非バッチ処理している場合または**IBTBatchTransmitter**はバッチ処理する場合。  
  
 バッチ化された送信アダプターおよびバッチ化されていない送信アダプターで実装する必要のあるインターフェイスを次の図に示します。  
  
 ![](../core/media/transmitterinterfaces.gif "TransmitterInterfaces")