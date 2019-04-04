---
title: 'シングル サインオン: イベント 10565 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d279491-dc0d-44c4-a77e-a67498a3481d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d31b639853b845169c3360ec6367aee120a266d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008003"
---
# <a name="single-sign-on-event-10565"></a>シングル サインオン: イベント 10565
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                           エンタープライズ シングル サインオン                                                                                           |
| 製品バージョン |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                           |
|    イベント ID     |                                                                                                     10565                                                                                                     |
|  イベント ソース   |                                                                                                    ENTSSO                                                                                                     |
|    コンポーネント    |                                                                                                      なし                                                                                                      |
|  シンボル名  |                                                                                       SSO_ERROR_SECRET_VALIDATE_FAILED                                                                                        |
|  メッセージ テキスト   | シークレットをレジストリから読み込めませんでした。 SSO サービスのサービス アカウントが変更されたか、シークレットが壊れている可能性があります。 バックアップ ファイルからシークレットを復元してください。%r<br /><br /> MSID: %1 |
  
## <a name="explanation"></a>説明  
 システムの管理者が、SSO サービス アカウントを変更し、暗号化を解除できないようにしている可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 SSO サービス アカウントを変更した管理者を見つけて、バックアップ ファイルからシークレットを復元します。 シークレットを復元する方法の詳細については、[マスター シークレットの管理](../core/managing-the-master-secret.md)を参照してください。