---
title: シングル サインオン:イベント 11043 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 128d68fb-1905-49b3-9b67-30a9442569cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d24076ea1354d923f16deed837a26d67997a2da4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400974"
---
# <a name="single-sign-on-event-11043"></a>シングル サインオン:イベント 11043
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                             エンタープライズ シングル サインオン                                                                                                                                             |
| 製品バージョン |                                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                             |
|    イベント ID     |                                                                                                                                                       11043                                                                                                                                                       |
|  イベント ソース   |                                                                                                                                                      ENTSSO                                                                                                                                                       |
|    コンポーネント    |                                                                                                                                                        なし                                                                                                                                                        |
|  シンボル名  |                                                                                                                                       SSO_WARN_PS_ADAPTER_REPORTED_FAILURE                                                                                                                                        |
|  メッセージ テキスト   | パスワード同期アダプターは、外部パスワードを変更中にエラーを報告します。 外部パスワードは SSO database.%r で更新されませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: % 3 %r<br /><br /> エラー メッセージ: % 4 %r<br /><br /> エラー コード: %5 |
  
## <a name="explanation"></a>説明  
 ENTSSO では、パスワードの変更をパスワード同期アダプターに送信するときに外部パスワードが正常に変更してください ENTSSO により SSO データベースで、前に。 この場合が行われませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告メッセージの情報をメモし、システム管理者に問い合わせてください。