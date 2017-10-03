---
title: "エラー メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error messages
- ports, error messages
- Catch Exception block [Orchestration Designer], error messages
- error messages, receiving
- messages, errors
- error messages, sending
ms.assetid: 33d62260-b5e0-4d14-b2d2-996733d588e7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4127fd5718ee910cb298436c0d0f7058ccba55b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fault-messages"></a>エラー メッセージ
要求 – 応答ポートにはエラー メッセージを関連付けることができます。これにより、要求の送信後に問題が発生した場合、応答サービスは応答の代わりにエラーを要求側に通知することができます。  
  
 要求 – 応答ポートの各操作では、任意の数の異なるエラーを処理できます。 エラー メッセージには任意の種類のメッセージを含めることができます。ただし、メッセージの種類は操作ごとに一意である必要があります。また、そのポート操作の応答で使用されない種類でなければなりません。  
  
## <a name="receiving-fault-messages"></a>エラー メッセージの受信  
 ポート操作で要求を送信して応答を受信する場合、そのポート操作を使用して複数の異なるエラー メッセージの種類を受信できます。  
  
 構成することができます、**例外のキャッチ**例外オブジェクト型と要求-応答ポート操作から適切なエラーを選択して、受信したエラー メッセージを処理するブロック。  
  
## <a name="sending-fault-messages"></a>エラー メッセージの送信  
 ポート操作で応答を受信して要求を送信する場合、そのポート操作を使用して複数の異なるエラー メッセージの種類を送信できます。  
  
 たとえば、オーケストレーションは、エラー状態が発生し、例外をスローする場合、内からエラー メッセージを送信することができます、**例外のキャッチ**例外を処理するブロック。 適切な種類のエラー メッセージを構築して、参加しているサービスに状況を伝達し、ポート操作の対応するエラーを使用する送信図形にそのエラー メッセージを指定します。  
  
## <a name="see-also"></a>参照  
 [例外](../core/exceptions.md)