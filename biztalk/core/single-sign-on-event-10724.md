---
title: "シングル サインオン: イベント 10724 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 022a6f73-a24b-4058-91a5-b831f6875409
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd9e65b18b66f119e3cc2acf7f078f17466e46b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10724"></a>シングル サインオン: イベント 10724
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10724|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_REPLAY_SECURITY_2|  
|メッセージ テキスト|再生ファイルまたは進行状況ファイルのセキュリティが元の値から変更されました。%r<br /><br /> ファイル名: %1 %r<br /><br /> 現在のファイルのセキュリティ: %2 %r<br /><br /> 元のファイル セキュリティ: %3|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、再生ファイルまたは進行状況ファイルのセキュリティが変更されたことを示します。  
  
 再生ファイルは再生ファイルのディレクトリに保存されます。 既定では、再生ファイルと再生ファイルのディレクトリの作成に SSO サービス アカウントが使用されます。 SSO により、再生ファイルと再生ファイルのディレクトリの作成以降、そのセキュリティ構成が変更されていないことが確認されます。 再生ファイルのディレクトリが異なるアカウントで作成された場合、パスワード同期によりそのディレクトリで再生ファイルを作成しようとすると、このエラーが返されることがあります。 ユーザーは再生ファイルと再生ファイルのディレクトリのセキュリティ構成を変更しないことを強くお勧めします。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
-   再生ファイルの作成に使用されたアカウントのアクセス許可を確認します。 これは、通常、SSO システム アカウントです。  
  
 詳細については、次のリソースを参照してください。  
  
-   [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  
  
-   [パスワード同期](../core/password-synchronization2.md)