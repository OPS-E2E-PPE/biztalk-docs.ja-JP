---
title: シングル サインオン:イベント 10589 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fe962bb-e9bb-4107-a5fb-21c180d54e21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160635fe7446a2fbac21edad332b4c87cd86e1b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400167"
---
# <a name="single-sign-on-event-10589"></a>シングル サインオン:イベント 10589
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                     エンタープライズ シングル サインオン                                                                                                                     |
| 製品バージョン |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    イベント ID     |                                                                                                                               10589                                                                                                                               |
|  イベント ソース   |                                                                                                                              ENTSSO                                                                                                                               |
|    コンポーネント    |                                                                                                                                なし                                                                                                                                |
|  シンボル名  |                                                                                                                 SSO_ERROR_BACKUP_SECRET_REQUIRED                                                                                                                  |
|  メッセージ テキスト   | マスター シークレットがバックアップされていません。 マスター シークレットが失われると、SSO システムに保存されたすべての情報が完全に失われます。また、システムが正しく動作しなくなることがあります。 SSO 管理ツールを使用して、マスター シークレットをバックアップしてください。 |
  
## <a name="explanation"></a>説明  
 マスター シークレットがバックアップされていません。 マスター シークレットが失われると、SSO システムに保存されたすべての情報が完全に失われます。また、システムが正しく動作しなくなることがあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 マスター シークレットのバックアップについては、次を参照してください。[マスター シークレットの管理](../core/managing-the-master-secret.md)します。