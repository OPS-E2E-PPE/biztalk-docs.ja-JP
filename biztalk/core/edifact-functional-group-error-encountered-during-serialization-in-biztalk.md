---
title: シリアル化中に発生したエラーです。 Edifact 機能グループが、次のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed81bc79-d99c-4305-805f-ab38eae91ea0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e8750a1ae4070543a9463b95827f14d10ab5180
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530787"
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a>シリアル化中に発生したエラーです。 Edifact 機能グループには、次のエラーがありました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                  |
| 製品バージョン |                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                              |
|    イベント ID     |                                                                                          -                                                                                          |
|  イベント ソース   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                |
|    コンポーネント    |                                                                                     EDI エンジン                                                                                      |
|  シンボル名  |                                                                            EfactFunctionalGroupSendError                                                                            |
|  メッセージ テキスト   | シリアル化中に発生したエラーです。 Edifact 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI 送信パイプラインでは、グループに示されたエラーのため、送信 EDIFACT インターチェンジ内の機能グループをシリアル化するときに、エラーが発生したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用して機能グループでエラーを特定し、ドキュメントで問題の解決方法を確認します。