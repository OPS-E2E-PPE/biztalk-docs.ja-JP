---
title: 修復と再送信メッセージを ESB 管理ポータルを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43091cbd-77d1-4cbd-9190-2d423ce7d4df
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5648213d459cbfbacef6db580f44efd5e2f46b3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400225"
---
# <a name="repairing-and-resubmitting-messages-using-the-esb-management-portal"></a>ESB 管理ポータルを使用してメッセージを再送信を修復し、
このユース ケースで、事前構成済み送信ポートで使用、ESB エラー プロセッサ パイプライン、オーケストレーションまたは Microsoft BizTalk の失敗のメッセージのルーティング メカニズムによって生成されたエラー メッセージ、例外ハンドラーによって生成された ESB フォールト メッセージを受信するを送信します。サーバー。 ESB エラー プロセッサは、正規化、拡充、および ESB 管理ポータルのデータベースにルーティングします。 ポータルでは、エラー メッセージの受信には、データベースを監視し、処理の失敗をサブスクライブしているユーザーに通知するアラートを生成することができます。 ユーザーはポータル エラー ビューアーでエラー メッセージを開き、メッセージの内容を編集および図 1 に示すように、処理には、メッセージを再実行してください。  
  
 ![メッセージの修復](../esb-toolkit/media/ch3-repairingmessages.gif "Ch3 RepairingMessages")  
  
 **図 1**  
  
 **ESB 管理ポータルを使用してメッセージを再送信を修復し、**  
  
 ESB 管理ポータルを使用するサンプルとして含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 編集し、メッセージを再送信の完全なグラフィカル環境を提供しますアラート、通知、およびメッセージ再送信の監査もサポートしています。  
  
 詳細については、次を参照してください。[例外とエラー メッセージを使用する](../esb-toolkit/working-with-exceptions-and-fault-messages.md)します。