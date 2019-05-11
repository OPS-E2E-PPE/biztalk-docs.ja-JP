---
title: シングル サインオン:イベント 10594 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f4c6041-39a8-49bc-b39e-66cb6eb2efae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c2f70c563113b7b7473d86046f2ac78eec4ea4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397853"
---
# <a name="single-sign-on-event-10594"></a>シングル サインオン:イベント 10594
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                 エンタープライズ シングル サインオン                                                                                  |
| 製品バージョン |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    イベント ID     |                                                                                           10594                                                                                            |
|  イベント ソース   |                                                                                           ENTSSO                                                                                           |
|    コンポーネント    |                                                                                            なし                                                                                             |
|  シンボル名  |                                                                              SSO_WARN_TICKET_VALIDATE_FAILED                                                                               |
|  メッセージ テキスト   | チケットの検証に失敗しました。 送信者名はチケット issuer.%r の一致する必要があります。<br /><br /> アプリケーション名: %1 %r<br /><br /> %2 のチケットの発行元: %r<br /><br /> 送信者名: %3 |
  
## <a name="explanation"></a>説明  
 チケットを検証するためには、(警告メッセージ) にチケットの発行元"と"送信者名フィールドに一致する必要があります。 ただし、BizTalk の信頼されていないホストを介してメッセージを送信する場合は、送信者名は、信頼されていない BizTalk ホストの名前に変更を取得し、チケットは検証されません。  
  
## <a name="user-action"></a>ユーザーの操作  
 エンタープライズ シングル サインオンを使用する場合は、メッセージが信頼されている BizTalk ホストのみを介して送信されていることを確認します。 これにより、メッセージのデータの改ざんのリスクが低減されます。  
  
 シナリオでは、セキュリティへの影響を完全に理解している場合は、このアプリケーションの検証をオフにすることができます。 検証は管理オプションであり、システムまたはこの特定のアプリケーションに対してだけ、オフにすることであることに注意してください。