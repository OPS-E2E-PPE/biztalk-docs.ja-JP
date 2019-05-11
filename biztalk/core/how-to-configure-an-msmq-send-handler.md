---
title: MSMQ 送信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send handlers
- configuring [MSMQ adapters], send handlers
- send handlers, MSMQ adapters
ms.assetid: 21917596-f27a-473b-859e-186ab5f4cd94
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f1ca5c7eb79f38671cc7e257b184125740ed0d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386429"
---
# <a name="how-to-configure-an-msmq-send-handler"></a>MSMQ 送信ハンドラーを構成する方法
送信ハンドラーを MSMQ のグローバル変数を変更するのには、次の手順を使用します。  
  
> [!NOTE]
>  各ホストには、1 つだけ送信ハンドラーが関連付けられていることができます。  
  
### <a name="to-change-global-variables-for-an-msmq-send-handler-by-using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールを使用してグローバル変数を MSMQ 送信ハンドラーを変更  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。  
  
2.  展開したアダプターの一覧でクリックして**MSMQ**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**いる送信ハンドラー、関連付けられているとする をクリックし、ホストを選択します**プロパティ**します。  
  
4.  **MSMQ トランスポートのプロパティ** ダイアログ ボックスで、値を入力**バッチ サイズ**します。  
  
     MSMQ 送信ハンドラーは、指定されたを使用して、送信先キューにメッセージを送信**バッチ サイズ**パラメーター。 既定の**バッチ サイズ**値は 5 です。  
  
5.  をクリックして**OK**  をクリック**ok**を閉じるためにもう一度、**アダプター ハンドラーのプロパティ** ダイアログ ボックス。