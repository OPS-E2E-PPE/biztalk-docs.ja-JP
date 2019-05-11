---
title: インターチェンジ構造エラーが、最初の機能グループの前に |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12202148-0a32-464e-8dbd-d01b9ba530eb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051323ef4c1ff6456595e34d6989e0183f050766
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254372"
---
# <a name="the-interchange-had-a-structural-error-in-before-the-first-functional-group"></a>インターチェンジ構造エラーが、最初の機能グループの前に
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                        |
| 製品バージョン |                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                    |
|    イベント ID     |                                                                -                                                                 |
|  イベント ソース   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                      |
|    コンポーネント    |                                                            EDI エンジン                                                            |
|  シンボル名  |                                           X12InterchangeStructuralErrorBefore1stGroup                                            |
|  メッセージ テキスト   | Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' で/最初の機能グループの前に構造エラーが |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、次の理由の 1 つの受信のインターチェンジを受信パイプラインが処理できなかったことを示します。  
  
-   インターチェンジ、該当するスキーマに準拠していなかったために、ISA および IEA セグメントまたはインターチェンジの最初の機能グループのいずれかで構造エラーが発生しました。  
  
-   (Baseartifacts.dll 内の) 内の X12ServiceSchema が展開されていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   ISA インターチェンジ変更の送信元および IEA セグメントまたは最初の機能グループがある、該当するスキーマに準拠するようにし、インターチェンジを再送信します。  
  
-   BaseArtifacts.dll に X12ServiceSchema が含まれていることと、X12ServiceSchema が展開されることを確認します。 これを行うには、BizTalk Server 管理コンソールを開き、開き、BizTalk EDI アプリケーション ノード、[スキーマ] ノード、X12ServiceSchema が表示されていることを確認しています。