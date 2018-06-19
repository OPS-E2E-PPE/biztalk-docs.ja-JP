---
title: 'シングル サインオン: イベント 10718 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de075c59-8396-48d1-be55-79303f83f984
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4bf86f4db59033b1ee4202c739ffeda43a587e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271786"
---
# <a name="single-sign-on-event-10718"></a>シングル サインオン: イベント 10718
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10718|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_REPLAY_INCORRECT_ADAPTER|  
|メッセージ テキスト|再生ファイルまたは進行ファイルに破損が検出されました。%r<br /><br /> ファイル名: %1 %r<br /><br /> クリアなアダプタ名: %2 %r<br /><br /> アダプター名を暗号化解除: %3|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、再生ファイルまたは進行状況ファイルで破損が検出されたことを示します。  
  
 再生ファイルは特定のパスワード同期アダプターに対して格納され、その特定のアダプターとして再生できます。 アダプター名は、クリア形式と暗号化形式の両方で格納されます。 このメッセージは、再生ファイルが再生のために暗号化解除されたときに、暗号化解除されたアダプター名がアダプター名と一致しなかったことを示します。 これは、再生ファイルが破損していること、または改ざんされた可能性があることを示す場合があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
-   再生ファイルの内容が変更されている可能性がある理由を調べ、バックアップが存在するかどうかを確認します。  
  
-   SSO マスター シークレットが変更されたかどうか、または SSO サービス アカウントが変更されたかどうかを確認します。これらは暗号化の動作に影響する場合があります。  
  
-   再生ファイルを削除します。  
  
 詳細については、次のリソースを参照してください。  
  
-   [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  
  
-   [パスワード同期](../core/password-synchronization2.md)