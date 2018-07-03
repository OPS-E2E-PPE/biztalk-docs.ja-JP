---
title: 'シングル サインオン: イベント 10683 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83cd1b96-cd79-4ddc-952b-94a7de216666
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a8a769e9cf74a3d0119ca814d7201c1e14e7304
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978307"
---
# <a name="single-sign-on-event-10683"></a>シングル サインオン: イベント 10683
## <a name="details"></a>詳細  

|                 |                                                                          |
|-----------------|--------------------------------------------------------------------------|
|  製品名   |                        エンタープライズ シングル サインオン                         |
| 製品バージョン |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]        |
|    イベント ID     |                                  10683                                   |
|  イベント ソース   |                                  ENTSSO                                  |
|    コンポーネント    |                                   N\A                                    |
|  シンボル名  |                   SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD                   |
|  メッセージ テキスト   | すぎたため、再生ファイルが削除された old.%r<br />再生ファイル: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、再生ファイルが古すぎたため、削除されたことを示します。 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 この場合、パスワード変更は一時的な暗号化ファイル保存され、再び使用可能になったときに、SSO データベースに対して再生されます。 SSO データベースに対してファイルを再生するときに、古すぎるファイルが検出された場合、そのファイルは破棄されます。 すべての古いパスワードの変更は、SSO パスワード同期システムによって破棄されます。`password sync age`パスワードの最大有効期間の変更要求およびコマンド ライン ツールを使用して制御できるパラメーターを決定します**ssoconfig-syncage**または SSO 管理 MMC。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザーの操作は必要ありません。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)
