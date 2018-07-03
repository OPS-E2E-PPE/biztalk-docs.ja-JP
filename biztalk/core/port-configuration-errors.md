---
title: ポートの構成エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92eae0d8-a0c4-4f8c-b91a-fd98b9f6931a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8cc3c8763115e93387bed5195f234bf4a070b9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986907"
---
# <a name="port-configuration-errors"></a>ポート構成エラー
診断および WCF のポート構成エラーを解決するための情報です。  

## <a name="cannot-merge-operation-due-to-communication-pattern-conflict"></a>通信方式が競合しているため、操作を結合できません
  
|                 |                                                         詳細                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| 製品バージョン |                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                |
|    イベント ID     |                                                            0                                                            |
|  イベント ソース   |                                                            0                                                            |
|    コンポーネント    |                                                            0                                                            |
|  シンボル名  |                                                            0                                                            |
|  メッセージ テキスト   | 操作を結合できません"{0}"通信方式が競合が原因です。  すべての操作は一方向または要求 - 応答方式に従う必要があります。 |
  
### <a name="explanation"></a>説明  
 このエラーは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、通信方式が異なるポートの種類と結合しようとすると表示されます。  
  
### <a name="user-action"></a>ユーザーの操作  
 ポート構成ウィザードを使用すると、結合されるすべてのポートは、同じ通信方式 (一方向または要求 - 応答) になります。  
  
 ポートの構成の詳細については、次を参照してください。[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)します。
 
## <a name="port-types-that-have-a-combination-of-one-way-and-request-response-operations-are-not-allowed"></a>一方向の操作および要求 - 応答の操作の組み合わせを保持するポートの種類は許可されていません 
  
|                 |                                                                                詳細                                                                                |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| 製品バージョン |                                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                       |
|    イベント ID     |                                                                                   0                                                                                   |
|  イベント ソース   |                                                                                   0                                                                                   |
|    コンポーネント    |                                                                                   0                                                                                   |
|  シンボル名  |                                                                                   0                                                                                   |
|  メッセージ テキスト   | 一方向の操作および要求 - 応答の操作の組み合わせを保持するポートの種類は許可されていません。 サービスの説明を修正"{0}「ポートの種類」{1}"し、ウィザードを再実行 |
  
### <a name="explanation"></a>説明  
 このエラーは、使用するサービスに、一方向と双方向 (つまり要求-応答) の両方があることを示します。  
  
### <a name="user-action"></a>ユーザーの操作  
 適切な操作 (両方ではなく、一方向または要求-応答) でサービスを修正して使用します (使用する WCF サービスを所有している場合)。 それ以外の場合、サービス プロバイダーに問い合わせてください。
