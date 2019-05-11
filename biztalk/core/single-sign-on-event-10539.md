---
title: シングル サインオン:イベント 10539 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a67f5719-da7c-4ae0-a6fe-ff7b653a184d
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbae36ca6e261fab1b7ae4e691f64da2bf9ba718
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392915"
---
# <a name="single-sign-on-event-10539"></a>シングル サインオン:イベント 10539
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10539                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                             CO                             |
|  シンボル名  |              SSO_WARN_SSO_TICKETS_NOT_ALLOWED              |
|  メッセージ テキスト   |        SSO システムに対しては、チケットが有効にできません。         |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO チケットの使用が有効でないことを示します。 SSO の使用を許可するチケットは、SSO システムの省略可能な機能です。 この機能は、SSO システムで有効になっていません。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- SSO システムに対してチケットを有効にする、SSO 管理者に問い合わせてください。 これ行う SSO 管理ツール (GUI またはコマンドライン) を使用します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md)  

- [SSO の使用](../core/using-sso.md)
