---
title: 'シングル サインオン: イベント 10687 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b3fe2c-a7ba-47e1-a753-4eaa64b01a60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 368e9bbad42e49ebd71bc1a581b0fb18bbcc2d5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270514"
---
# <a name="single-sign-on-event-10687"></a>シングル サインオン: イベント 10687
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10687|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_INFO_REPLAY_COMPLETE|  
|メッセージ テキスト|保存された外部パスワード変更の再生が完了しました。%r<br /><br /> 再生ファイル: %1 %r<br /><br /> 追加データ: %2|  
  
## <a name="explanation"></a>説明  
 この情報イベントは、SSO によって保存された外部パスワード変更ファイルの再生が完了したことを示します。 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。  
  
## <a name="user-action"></a>ユーザーの操作  
  
-   ユーザーの操作は必要ありません。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  
  
-   [パスワード同期](../core/password-synchronization2.md)