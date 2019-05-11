---
title: シングル サインオン:イベント 10545 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6695a46f2116045e5aec58514ac110c6a2948f66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243488"
---
# <a name="single-sign-on-event-10545"></a>シングル サインオン:イベント 10545
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10545                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                             CO                             |
|  シンボル名  |             SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED             |
|  メッセージ テキスト   |        SSO システムに対しては、チケットが有効にできません。         |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO システムに対してチケットが有効ではないことを示します。 システム レベルでチケットが無効になっている場合は、チケット発行使用できません関連アプリケーション レベルか。 システム レベルでチケットを有効にして、関連アプリケーション レベルで無効にすることになります。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- SSO システム レベルでチケットを有効にします。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO チケット](../core/sso-tickets.md)  

- [SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md)
