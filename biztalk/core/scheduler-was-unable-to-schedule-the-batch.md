---
title: "スケジューラはバッチをスケジュールできませんでした |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ac6d79c-c995-4c95-a4da-ee2f50b9a13a
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bef1df18d88f8497fde440383d63bc64eefdd69a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scheduler-was-unable-to-schedule-the-batch"></a>スケジューラはバッチをスケジュールできませんでした
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|-|  
|メッセージ テキスト|スケジューラはバッチをスケジュールできませんでした|  
  
## <a name="explanation"></a>説明  
 このエラーは、スケジューラが次回のバッチ リリースを特定できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、バッチ リリース スケジュールが有効になっていることを確認します。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、] をクリック**パーティ**です。  
  
3.  適切なパーティを右クリックします。  
  
4.  **[プロパティ]**をクリックします。  
  
5.  [*パーティ名*]**パーティ プロパティ**ダイアログ ボックスで、左側のウィンドウでをクリックして**送信ポート**です。  
  
6.  [送信ポートの名前を入力、**送信ポート**] ボックスの一覧です。  
  
7.  **[OK]**をクリックします。