---
title: 修復と再送信メッセージの ESB 管理ポータルを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: 61602fb41a2c6754fe6d77d249e2ec8c2f40cd39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295258"
---
# <a name="repairing-and-resubmitting-messages-using-the-esb-management-portal"></a>修復し、ESB の管理ポータルを使用してメッセージを再送信
このユース ケースで、構成済み送信ポートで使用、ESB フォールト プロセッサ送信、オーケストレーションまたはメッセージのルーティングの失敗のメカニズムでは、Microsoft BizTalk によって生成されたエラー メッセージ、例外ハンドラーによって生成された ESB フォールト メッセージを受信するパイプラインサーバー。 ESB フォールト プロセッサは、正規化、拡充、および、ESB 管理ポータルのデータベースにルーティングします。 ポータルでは、受信のエラー メッセージをデータベースを監視し、処理エラーの定期受信済みのユーザーに通知するアラートを生成することができます。 ユーザーは、ポータルの フォールト ビューアーで、エラー メッセージを開いて、メッセージの内容を編集および図 1 に示すように、処理のためにメッセージを再送信します。  
  
 ![メッセージの修復](../esb-toolkit/media/ch3-repairingmessages.gif "Ch3 RepairingMessages")  
  
 **図 1**  
  
 **修復し、ESB の管理ポータルを使用してメッセージを再送信**  
  
 使用するサンプルとして含まれている ESB 管理ポータル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 編集し、メッセージを再送信の完全なグラフィカル環境を提供します。また、アラート、通知、およびメッセージ再送信の監査もサポートします。  
  
 詳細については、次を参照してください。[例外とエラー メッセージを使用する](../esb-toolkit/working-with-exceptions-and-fault-messages.md)です。