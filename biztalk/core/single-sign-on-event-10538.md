---
title: シングル サインオン:イベント 10538 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9d1a1b8b09d9bc4725c55060aebe705f256e691
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250378"
---
# <a name="single-sign-on-event-10538"></a>シングル サインオン:イベント 10538
## <a name="details"></a>詳細  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  製品名   |                         エンタープライズ シングル サインオン                         |
| 製品バージョン |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    イベント ID     |                                   10538                                   |
|  イベント ソース   |                                  ENTSSO                                   |
|    コンポーネント    |                                    CO                                     |
|  シンボル名  |                           SSO_WARN_APP_DISABLED                           |
|  メッセージ テキスト   | アプリケーションは、現在 disabled.%r です。<br /><br /> アプリケーション名: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO 関連アプリケーションが無効になっている、アプリケーション管理者によってを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- SSO 関連アプリケーションを有効にする、アプリケーション管理者に問い合わせてください。 これ行う SSO 管理ツール (GUI またはコマンドライン) を使用します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)  

- [関連アプリケーションを無効にする方法](../core/how-to-disable-an-affiliate-application.md)
