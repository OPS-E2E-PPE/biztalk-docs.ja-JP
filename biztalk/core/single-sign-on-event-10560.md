---
title: "シングル サインオン: イベント 10560 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8677a807-2973-4753-8816-c93c45697d92
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d630dccdd21aaade843d4aa8fd7026d05fd71da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10560"></a>シングル サインオン: イベント 10560
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10560|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_ERROR_BACKUP_SECRET_FAILED|  
|メッセージ テキスト|マスター シークレットをバックアップできませんでした。%r<br /><br /> ファイル名: %1 %r<br /><br /> 現在の MSID: %2 %r<br /><br /> 以前の MSID: %3 %r<br /><br /> クライアント ユーザー: %4 %r<br /><br /> エラー コード: %5|  
  
## <a name="explanation"></a>説明  
 マスター シークレットをバックアップしようとしましたが失敗しました。 このバックアップを実行しようとしたユーザーが使用したアクセス許可、パス、またはディレクトリが正しくない可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 マスター シークレットのバックアップについては、次を参照してください。[マスタ シークレットの管理](../core/managing-the-master-secret.md)です。