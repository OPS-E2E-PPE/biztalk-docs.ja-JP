---
title: 'シングル サインオン: イベント 10728 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f579189c-c9a5-4d2c-a3d5-f0ba03c5a3ef
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5e37738d0bf566b2faf3b5b65c1152cd3ef6405
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995291"
---
# <a name="single-sign-on-event-10728"></a>シングル サインオン: イベント 10728
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                     エンタープライズ シングル サインオン                                                                                                                     |
| 製品バージョン |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    イベント ID     |                                                                                                                               10728                                                                                                                               |
|  イベント ソース   |                                                                                                                              ENTSSO                                                                                                                               |
|    コンポーネント    |                                                                                                                                N\A                                                                                                                                |
|  シンボル名  |                                                                                                                         SSO_ERROR_VERSION                                                                                                                         |
|  メッセージ テキスト   | このバージョンの SSO サーバーは SSO データベースと互換性がありません。 マスター シークレット サーバーをアップグレードしてください。%r<br /><br /> SQL Server 名: %1 %r<br /><br /> SSO データベース名: % 2 %r<br /><br /> SSO データベースのバージョン: % 3 %r<br /><br /> ために必要なバージョン: %4 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO サーバーのバージョンが SSO データベース (の作成に使用されたバージョン) より新しいことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- SSO マスター シークレット サーバーをアップグレードして、この SSO サーバーの現在のバージョンと一致させます。 これにより、SSO データベースが現在のバージョンにアップグレードされます。  

  詳細については、次のリソースを参照してください。  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
