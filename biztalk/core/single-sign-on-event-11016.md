---
title: 'シングル サインオン: イベント 11016 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3963b706-168d-438d-a068-637f8a6b7b0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96f39cba26da1b3e03c7259643c3dcf2704bbdf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974515"
---
# <a name="single-sign-on-event-11016"></a>シングル サインオン: イベント 11016
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                   エンタープライズ シングル サインオン                                                                                                                                                                    |
| 製品バージョン |                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                   |
|    イベント ID     |                                                                                                                                                                             11016                                                                                                                                                                              |
|  イベント ソース   |                                                                                                                                                                             ENTSSO                                                                                                                                                                             |
|    コンポーネント    |                                                                                                                                                                              なし                                                                                                                                                                               |
|  シンボル名  |                                                                                                                                                                RPC 拡張エラー情報%r                                                                                                                                                                |
|  メッセージ テキスト   | %1%r<br /><br /> エラー コード: %2<br /><br /> AuthzInitializeContextFromSid 関数が ERROR_ACCESS_DENIED で失敗しました。 これは、SSO サーバーが実行されているサービス アカウントに、Active Directory 内のグループ メンバーシップを確認するのに十分なアクセス許可がないことを意味しています。 この問題の修正方法については、ドキュメントを確認してください。%r |
  
## <a name="explanation"></a>説明  
 SSO サーバーが実行されているサービス アカウントに、Active Directory 内のグループ メンバーシップを確認するのに十分なアクセス許可がないことを意味しています。  
  
## <a name="user-action"></a>ユーザーの操作  
 参照してください[SSO サーバー](../core/sso-server.md) SSO ドキュメント。