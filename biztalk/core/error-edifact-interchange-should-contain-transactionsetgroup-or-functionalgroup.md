---
title: Edifact インターチェンジの必要がありますが含まれている TransactionSetGroup または FunctionalGroup Xml タグ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34318133-211f-422d-acdf-b841ece5d2b0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5736a9146a88dd9c9dac6747e381fccc88f18d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979331"
---
# <a name="edifact-interchange-should-have-contained-transactionsetgroup-or-functionalgroup-xml-tags"></a>EDIFACT インターチェンジには TransactionSetGroup または FunctionalGroup XML タグが含まれている必要があります
## <a name="details"></a>詳細  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  製品名   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| 製品バージョン |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    イベント ID     |                                             -                                             |
|  イベント ソース   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI   |
|    コンポーネント    |                                        EDI エンジン                                         |
|  シンボル名  |                                             -                                             |
|  メッセージ テキスト   | EDIFACT インターチェンジには TransactionSetGroup または FunctionalGroup XML タグが含まれている必要があります |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、TransactionSetGroup または FunctionalGroup タグがインターチェンジ XML ファイルに含まれていなかったため、送信パイプラインが保存された EDIFACT バッチ インターチェンジを処理できなかったことを示します。  
  
 BizTalk が保存されているバッチ インターチェンジを処理する場合、インターチェンジの XML ファイルで、トランザクション セットのグループまたはグループのグループに XML タグが付与されます。 トランザクション セットのグループには TransactionSetGroup タグが設定されます。 グループのグループには、FunctionalGroup タグが付与されます。 このエラー状態は、受信パイプラインとパススルー送信パイプラインを使用して、保存されたバッチを設定する場合に発生します。 タグは受信パイプラインによって設定され、送信パイプラインによって除去されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、保存されたバッチ用に生成された XML ファイルで、TransactionSetGroup タグ (複数のトランザクション セットがあるグループ用)、FunctionalGroup タグ (複数のグループ用)、またはその両方に整形式の XML 構造が使用されていることを確認します。