---
title: エラー メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
- ports, error messages
- Catch Exception block [Orchestration Designer], error messages
- error messages, receiving
- messages, errors
- error messages, sending
ms.assetid: 33d62260-b5e0-4d14-b2d2-996733d588e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fe3ab052612166b55fb966507a4a4c95b1b8f81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388079"
---
# <a name="fault-messages"></a>エラー メッセージ
要求-応答ポートは、問題が発生した要求が送信される場合、応答サービスは、要求元の応答の代わりにエラーを通信できるように、それらに関連付けられているエラー メッセージを持つことができます。  
  
 要求-応答ポートの各操作では、任意の数の異なるエラーを処理できます。 エラー メッセージは、任意のメッセージ型を持つことができますが、メッセージの種類は、操作に対して一意である必要があり、そのポート操作の応答で使用される型でなければなりません。  
  
## <a name="receiving-fault-messages"></a>エラー メッセージの受信  
 ポート操作で要求を送信応答を受信する場合は、1 つまたは複数の異なるエラー メッセージの種類の受信に使用できます。  
  
 構成することができます、**例外のキャッチ**例外オブジェクト型と要求-応答ポート操作から適切なエラーを選択して、受信したエラー メッセージを処理するためにブロックします。  
  
## <a name="sending-fault-messages"></a>エラー メッセージの送信  
 ポート操作の応答を受信要求を送信する場合は、1 つまたは複数の異なるエラー メッセージの種類の送信に使用できます。  
  
 たとえば、オーケストレーションは、エラー状態が発生し、例外をスローする場合、内からエラー メッセージを送信することができます、**例外のキャッチ**例外を処理するブロック。 参加しているサービスに状況を伝達するために適切な種類のエラー メッセージを構築し、ポート操作で対応するフォールトが使用する送信図形にそのエラー メッセージを指定します。  
  
## <a name="see-also"></a>参照  
 [例外](../core/exceptions.md)