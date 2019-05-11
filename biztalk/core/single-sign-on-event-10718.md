---
title: シングル サインオン:イベント 10718 |Microsoft Docs
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
ms.openlocfilehash: 331d78687d7948a4f37ab3b16e4a95e42c5e209c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397211"
---
# <a name="single-sign-on-event-10718"></a>シングル サインオン:イベント 10718
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                     エンタープライズ シングル サインオン                                                                     |
| 製品バージョン |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    イベント ID     |                                                                               10718                                                                               |
|  イベント ソース   |                                                                              ENTSSO                                                                               |
|    コンポーネント    |                                                                                該当なし                                                                                |
|  シンボル名  |                                                                SSO_ERROR_REPLAY_INCORRECT_ADAPTER                                                                 |
|  メッセージ テキスト   | 再生または進行状況 file.%r で破損が検出されました<br /><br /> ファイル名: %1 %r<br /><br /> クリアなアダプタ名: % 2 %r<br /><br /> アダプター名を復号化: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、再生ファイルまたは進行ファイルで破損が検出されたことを示します。  

 再生ファイルは、特定のパスワード同期アダプターの格納されているため、その特定のアダプターとして再生できます。 アダプター名は、フォームのクリアと暗号化の両方に格納されます。 このメッセージは、こと、再生ファイルが再生の復号化、復号化されたアダプター名が一致しません、アダプター名を示します。 これにより、されているといくつかの破損または再生ファイルの可能な改ざんは提示されます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- 再生ファイルの内容をされた可能性がありますを決定する、変更は、バックアップが存在するかどうかを参照してください。  

- チェックの場合は、SSO マスター シークレットが変更されたか、SSO サービス アカウントが変更された、暗号化の動作に影響する可能性があります。  

- 再生ファイルを削除します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)
