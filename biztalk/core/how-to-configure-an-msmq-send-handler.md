---
title: "MSMQ 送信ハンドラーを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send handlers
- configuring [MSMQ adapters], send handlers
- send handlers, MSMQ adapters
ms.assetid: 21917596-f27a-473b-859e-186ab5f4cd94
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feacaec9d2794cf8806fa5156fe64b7290699faa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-msmq-send-handler"></a>MSMQ 送信ハンドラーを構成する方法
次の手順を実行して、MSMQ 送信ハンドラーのグローバル変数を変更します。  
  
> [!NOTE]
>  各ホストに関連付けられる送信ハンドラーは 1 つだけです。  
  
### <a name="to-change-global-variables-for-an-msmq-send-handler-by-using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールを使用して MSMQ 送信ハンドラーのグローバル変数を変更するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして**MSMQ**、右側のペインで、構成する送信ハンドラを右クリックしをクリック**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、使用する送信ハンドラー、関連付けられているとする をクリックし、ホストを選択**プロパティ**です。  
  
4.  **MSMQ トランスポートのプロパティ** ダイアログ ボックスで、値を入力**バッチ サイズ**です。  
  
     MSMQ 送信ハンドラーが指定して、送信先キューにメッセージを送信する**バッチ サイズ**パラメーター。 既定値**バッチ サイズ**値は 5 です。  
  
5.  をクリックして**OK**  をクリック**ok**を閉じます、**アダプター ハンドラーのプロパティ** ダイアログ ボックス。