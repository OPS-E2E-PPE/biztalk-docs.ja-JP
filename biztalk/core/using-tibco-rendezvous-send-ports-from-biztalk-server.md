---
title: "BizTalk Server から TIBCO Rendezvous 送信ポートの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, handling
- message handling
- BizTalk Server, using send ports from
- send ports, using from BizTalk Server
- messages, generating
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e11657e8e15ac0739124178e85f0c7c5c0a70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-send-ports-from-biztalk-server"></a>BizTalk Server からの TIBCO Rendezvous 送信ポートの使用
送信ポートはあらゆる種類のメッセージを送信できます。 BizTalk Server で Microsoft BizTalk Adapter for TIBCO Rendezvous を介してメッセージを送信する場合、アダプターはメッセージ コンテキストのプロパティ値に基づいてメッセージを生成するか、既定値を使用して、メッセージを指定されたサブジェクトに送信します。  
  
> [!NOTE]
>  TIBCO Rendezvous のドキュメントに従って、送信サブジェクト名ではワイルドカード文字はサポートされていません。  
  
## <a name="message-handling"></a>メッセージの処理  
 アダプターは状態を維持し、それに従って BizTalk Server の受信メッセージを処理します。  
  
-   トランスポートのエラーでメッセージを送信できない場合、BizTalk Server に対して後で再送信するように指示されます。  
  
-   アダプターがまだ初期化中であるためにメッセージを送信できない場合、BizTalk Server メッセージはキューに配置されます。 初期化に失敗した場合、BizTalk Server は後で再送信するように指示されます。  
  
## <a name="message-generation"></a>メッセージの生成  
 送信アダプターを使用する場合、BizTalk Adapter for TIBCO Rendezvous はメッセージのターゲットの名前空間およびルート要素を無視します。 アダプターがメッセージを送信する場合、アダプターはペイロードをそのまま送信します。 アダプターが構造化 TIBCO Rendezvous メッセージを生成する場合、ルート要素の名前は無視されます (メッセージに名前はありません)。 いずれの場合も、アダプターはコンテキスト プロパティを使用して、メッセージを公開するときに使用するサブジェクトを検索します。  
  
 詳細については、次を参照してください。 [BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)](../core/biztalk-server-message-context-properties-send-handlers.md)と[TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)です。  
  
## <a name="see-also"></a>参照  
 [送信ポートの作成](../core/creating-send-ports2.md)   
 [TIBCO Rendezvous 送信ハンドラーを作成します。](../core/creating-tibco-rendezvous-send-handlers.md)