---
title: 'シングル サインオン: イベント 11010 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22fcd9f3-83bb-44b0-88fc-197c2ef3e72d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba07dde6b32ebb2f5d92365fcead94c0b4ecc66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965819"
---
# <a name="single-sign-on-event-11010"></a>シングル サインオン: イベント 11010
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                エンタープライズ シングル サインオン                                                                                |
| 製品バージョン |                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    イベント ID     |                                                                                          11010                                                                                          |
|  イベント ソース   |                                                                                         ENTSSO                                                                                          |
|    コンポーネント    |                                                                                           なし                                                                                           |
|  シンボル名  |                                                                               SSO_WARN_NOT_SSO_AFF_ADMIN                                                                                |
|  メッセージ テキスト   | クライアント ユーザーが SSO 関連管理者アカウントのメンバーではありません。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2\\% 3 %r<br /><br /> SSO 関連管理者: %4 |
  
## <a name="explanation"></a>説明  
 クライアント ユーザーが SSO 関連管理者アカウントのメンバーではありません。 この警告は、監査レベルが高に設定されている場合にのみ表示されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 この状況を解決するには、クライアント ユーザーを SSO 関連管理者アカウントのメンバーにする必要があります。 今後警告を表示しない場合は、監査レベルを低くします。