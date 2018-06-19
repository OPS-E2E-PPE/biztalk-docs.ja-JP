---
title: 'シングル サインオン: イベント 10682 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46f0f425-3946-4bac-a412-488c4afe460d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79aeff556fbbbbbbbcf41f63a37ab3b47311d697
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271410"
---
# <a name="single-sign-on-event-10682"></a>シングル サインオン: イベント 10682
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10682|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_REPLAY_INVALID_DIR_FOUND|  
|メッセージ テキスト|ディレクトリが見つかりました - 再生ファイルのディレクトリで ignored.%r がなります<br />ディレクトリ: %1|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、再生ファイル ディレクトリ内でディレクトリが見つかったことを示します。 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 ここではパスワードの変更は一時的な暗号化ファイルに格納され、これが再び使用可能なときに、SSO データベースに再生されます。 再生ファイル ディレクトリは、再生ファイルのみを格納することが想定されています。このエラー メッセージは、ディレクトリが見つかった場合に発行されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   コマンド ライン ツール ssoconfig -replayFiles を使用して、再生ディレクトリを変更します。  
  
-   使用中ではない場合は不適切なディレクトリを削除します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  
  
-   [パスワード同期](../core/password-synchronization2.md)