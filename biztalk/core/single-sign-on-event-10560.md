---
title: 'シングル サインオン: イベント 10560 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8677a807-2973-4753-8816-c93c45697d92
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82f9245b4eda9b6bf567aae1de2071d3e77aae04
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967755"
---
# <a name="single-sign-on-event-10560"></a>シングル サインオン: イベント 10560
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                  エンタープライズ シングル サインオン                                                                                  |
| 製品バージョン |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    イベント ID     |                                                                                            10560                                                                                            |
|  イベント ソース   |                                                                                           ENTSSO                                                                                            |
|    コンポーネント    |                                                                                             なし                                                                                             |
|  シンボル名  |                                                                               SSO_ERROR_BACKUP_SECRET_FAILED                                                                                |
|  メッセージ テキスト   | マスター シークレットをバックアップできませんでした。%r<br /><br /> ファイル名: %1 %r<br /><br /> 現在の MSID: % 2 %r<br /><br /> 以前の MSID: % 3 %r<br /><br /> クライアント ユーザー: % 4 %r<br /><br /> エラー コード: %5 |
  
## <a name="explanation"></a>説明  
 マスター シークレットをバックアップしようとしましたが失敗しました。 このバックアップを実行しようとしたユーザーが使用したアクセス許可、パス、またはディレクトリが正しくない可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 マスター シークレットのバックアップについては、[マスター シークレットの管理](../core/managing-the-master-secret.md)を参照してください。