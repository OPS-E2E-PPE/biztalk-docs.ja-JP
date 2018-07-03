---
title: 'シングル サインオン: イベント 10537 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c42a4f6-043b-4d4a-956a-a1c1407d2e33
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1945c419af7cc1cc8555224c25642a243c45edcf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004555"
---
# <a name="single-sign-on-event-10537"></a>シングル サインオン: イベント 10537
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10537                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                             CO                             |
|  シンボル名  |                   SSO_WARN_SSO_DISABLED                    |
|  メッセージ テキスト   |           SSO システムは現在無効になっています。            |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO 管理者が SSO システムを無効にしていることを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   

- SSO 管理者に問い合わせて、SSO システムを有効にします。 SSO を有効にするには、SSO 管理ツール (GUI またはコマンド ライン) を使用できます。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [SSO を有効にする方法](../core/how-to-enable-sso.md)  

- [SSO を無効にする方法](../core/how-to-disable-sso.md)
