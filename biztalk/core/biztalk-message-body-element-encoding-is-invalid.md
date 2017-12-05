---
title: "BizTalk メッセージ本文要素のエンコードが正しくありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b407e5c3-4655-4b2f-8ecc-30eb080ec47c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b1835371e5c042d3ddc46558cbf97970f6bfc6c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a>BizTalk メッセージ本文要素のエンコードは無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|BizTalk メッセージ本文要素のエンコード "{0}" は無効です。 エンコーディングが必要です"xml"、"base64"、"hex"、または"string"。|  
  
## <a name="explanation"></a>説明  
 このエラーは、送信メッセージには BizTalk 本文テンプレート オプションが使用されていますが、BizTalk 本文に指定されたエンコーディングの種類は無効であることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 エンコーディングの種類を構成するには、次の手順を実行します。  
  
#### <a name="to-configure-the-encoding-type"></a>エンコーディングの種類を構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブです。  
  
9. **送信 WCF メッセージ本文**セクションで、をクリックして、**テンプレート--テンプレートで指定されたコンテンツ**ラジオ ボタンをクリックします。 **XML**テキスト ボックスで、BizTalk 本文の形式である必要があります   
    \<**bts メッセージ本文の xmlns ="http://www.microsoft.com/schemas/bts2007"encoding =「[xml &#124; base64 &#124; 16 進数 &#124; 文字列]」/** \> (有効な値、xml &#124; base64 & # は、エンコード、大文字小文字が区別されます。#124; 16 進数 (&) #124 です。 文字列)