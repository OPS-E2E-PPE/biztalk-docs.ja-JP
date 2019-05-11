---
title: シングル サインオン:イベント 11016 |Microsoft Docs
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
ms.openlocfilehash: 01bf4d34a68680b391e49b465e44138fca81b210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267074"
---
# <a name="single-sign-on-event-11016"></a>シングル サインオン:イベント 11016
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                   エンタープライズ シングル サインオン                                                                                                                                                                    |
| 製品バージョン |                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                   |
|    イベント ID     |                                                                                                                                                                             11016                                                                                                                                                                              |
|  イベント ソース   |                                                                                                                                                                             ENTSSO                                                                                                                                                                             |
|    コンポーネント    |                                                                                                                                                                              なし                                                                                                                                                                               |
|  シンボル名  |                                                                                                                                                                RPC 拡張エラー情報 %r                                                                                                                                                                |
|  メッセージ テキスト   | % 1 %r<br /><br /> エラー コード: %2<br /><br /> AuthzInitializeContextFromSid 関数は、ERROR_ACCESS_DENIED で失敗しました。 これは、SSO サーバーが実行されているサービス アカウントに Active Directory でグループ メンバーシップを確認するための十分なアクセス許可がないことを意味します。 この problem.%r を修正する方法の詳細について、ドキュメントを確認してください。 |
  
## <a name="explanation"></a>説明  
 SSO サーバーが実行されているサービス アカウントには、Active Directory でグループ メンバーシップを確認するための十分なアクセス許可がありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 参照してください[SSO サーバー](../core/sso-server.md) SSO ドキュメント。