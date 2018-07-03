---
title: シリアル化中にエラーが発生しました。 Edifact 機能グループが、次のエラー |Microsoft Docs
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
ms.openlocfilehash: 0cd5ce1a94a47c5094862decfe1bb1dbb9c1efb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977603"
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a>シリアル化中にエラーが発生しました。 EDIFACT 機能グループに次のエラーがありました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                  |
| 製品バージョン |                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                              |
|    イベント ID     |                                                                                          -                                                                                          |
|  イベント ソース   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                |
|    コンポーネント    |                                                                                     EDI エンジン                                                                                      |
|  シンボル名  |                                                                            EfactFunctionalGroupSendError                                                                            |
|  メッセージ テキスト   | シリアル化中にエラーが発生しました。 Edifact 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、示されたエラーがグループで発生したため、送信 EDIFACT インターチェンジ内の機能グループのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用して機能グループのエラーを特定し、ドキュメントで問題解決の方法を確認してください。