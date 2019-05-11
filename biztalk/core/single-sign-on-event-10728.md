---
title: シングル サインオン:イベント 10728 |Microsoft Docs
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
ms.openlocfilehash: a9c7469a60ba0143f3e6674f5b140a452eebfe63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394335"
---
# <a name="single-sign-on-event-10728"></a>シングル サインオン:イベント 10728
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                     エンタープライズ シングル サインオン                                                                                                                     |
| 製品バージョン |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    イベント ID     |                                                                                                                               10728                                                                                                                               |
|  イベント ソース   |                                                                                                                              ENTSSO                                                                                                                               |
|    コンポーネント    |                                                                                                                                該当なし                                                                                                                                |
|  シンボル名  |                                                                                                                         SSO_ERROR_VERSION                                                                                                                         |
|  メッセージ テキスト   | このバージョンの SSO サーバーは、SSO データベースとの互換性がありません。 マスター シークレット server.%r をアップグレードしてください。<br /><br /> SQL Server 名: %1 %r<br /><br /> SSO データベース名: % 2 %r<br /><br /> SSO データベースのバージョン: % 3 %r<br /><br /> ために必要なバージョン: %4 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO サーバーのバージョンが (最初に作成されたバージョン) よりも新しいことを示します、SSO データベース。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- この SSO サーバーの現在のバージョンと一致する SSO マスタ シークレット サーバーをアップグレードします。 これにより、SSO データベースが、現在のバージョンにアップグレードされます。  

  詳細については、次のリソースを参照してください。  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
