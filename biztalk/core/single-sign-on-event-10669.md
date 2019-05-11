---
title: シングル サインオン:イベント 10669 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e88a583d-7385-42dd-841e-aa2d2215dd69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d0a9ab77f528060be25616eb8d80072402957a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397534"
---
# <a name="single-sign-on-event-10669"></a>シングル サインオン:イベント 10669
## <a name="details"></a>詳細  

|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                   エンタープライズ シングル サインオン                                                                   |
| 製品バージョン |                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    イベント ID     |                                                                             10669                                                                             |
|  イベント ソース   |                                                                            ENTSSO                                                                             |
|    コンポーネント    |                                                                              該当なし                                                                              |
|  シンボル名  |                                                            SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED                                                            |
|  メッセージ テキスト   | Windows password.%r を変更できませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: % 3 %r<br /><br /> エラー コード: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、Windows パスワードを変更する SSO が失敗したことを示します。 SSO は、Win32 関数のマッピングに関連付けられている Windows のパスワードを変更する netuserchangepassword を呼び出して関数を呼び出します。 この関数が失敗するとこのエラー メッセージが発行されます。 エラー コードは、NetUserChangePassword から返された 1 つになります。 詳細については MSDN では、この関数のマニュアルを参照してください。 エラーの最も多い原因は、古いパスワードが間違ってまたは、新しいパスワードが必要な Windows パスワード ポリシーを満たしていないことです。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- 古いパスワードを確認します。 古いパスワードが正しくない場合、コマンド ライン ツールまたは管理 MMC を使用して SSO データベースに手動で設定することができます。  

- 新しいパスワードが必要な Windows パスワード ポリシーを満たしていることを確認します。 パスワードが満たしていない場合し Windows パスワード ポリシーがパスワード フィルターの使用を検討します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期](../core/password-synchronization2.md)
