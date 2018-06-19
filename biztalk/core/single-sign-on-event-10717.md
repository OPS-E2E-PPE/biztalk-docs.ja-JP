---
title: 'シングル サインオン: イベント 10717 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70195251b599daebd50b57f0b137dd026dd032e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270362"
---
# <a name="single-sign-on-event-10717"></a>シングル サインオン: イベント 10717
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10717|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_NEW_REPLAY_DIR_FAILED|  
|メッセージ テキスト|再生ファイル ディレクトリを作成できませんでした。%r<br /><br /> クライアント ユーザー: %1 %r<br /><br /> 再生ファイル ディレクトリ: %2 %r<br /><br /> エラー コード: %3|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、再生ファイル ディレクトリを作成できなかったことを示します。  
  
 SSO サービスがパスワード同期アダプターからパスワード変更を受信すると、パスワード変更は SSO データベースに格納されます。 SSO データベースが一時的に使用できない場合は、パスワード変更はローカルの再生ファイルに保存されます。 再生ファイルは再生ファイルのディレクトリに保存されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
-   再生ファイル ディレクトリを確認し、再生ファイル ディレクトリが存在しない場合は、SSO サービスと同じサービス アカウントを使用して、手動で再生ファイル ディレクトリを作成してみます。 SSO サービスと同じアカウントを使用して再生ファイル ディレクトリを作成できない場合は、そのアカウントのアクセス許可を確認します。  
  
 詳細については、次のリソースを参照してください。  
  
-   [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  
  
-   [パスワード同期](../core/password-synchronization2.md)