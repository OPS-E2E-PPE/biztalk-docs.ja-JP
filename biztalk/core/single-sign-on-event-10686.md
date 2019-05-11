---
title: シングル サインオン:イベント 10686 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e71f2a-e51d-4736-b06a-117142d30dae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90306488cb77f40458cf0fccacae9050807a2e3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397385"
---
# <a name="single-sign-on-event-10686"></a>シングル サインオン:イベント 10686
## <a name="details"></a>詳細  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  製品名   |                         エンタープライズ シングル サインオン                         |
| 製品バージョン |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    イベント ID     |                                   10686                                   |
|  イベント ソース   |                                  ENTSSO                                   |
|    コンポーネント    |                                    該当なし                                    |
|  シンボル名  |                          SSO_INFO_REPLAY_STARTED                          |
|  メッセージ テキスト   | 格納されている外部パスワード changes.%r を再生します。<br /><br /> 再生ファイル: %1 |

## <a name="explanation"></a>説明  
 この情報イベントは、SSO が保存された外部パスワード変更ファイルを再生することを示します。 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)
