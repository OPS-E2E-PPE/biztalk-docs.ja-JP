---
title: FunctionalGroup または ServiceSchema はありません、無効な構造により Edifact インターチェンジの Xml シリアル化が失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 530faadd-e301-4743-b4b3-b04ba7578f1d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e7b7f6c93203e3b4122c7f99ed5936df7ab0af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388912"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-functionalgroup-or-serviceschema"></a>FunctionalGroup または ServiceSchema はありません、無効な構造により Edifact インターチェンジの Xml シリアル化が失敗しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| 製品バージョン |                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    イベント ID     |                                                                      -                                                                       |
|  イベント ソース   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                            |
|    コンポーネント    |                                                                  EDI エンジン                                                                  |
|  シンボル名  |                                                                      -                                                                       |
|  メッセージ テキスト   | 無効な構造により、EDIFACT インターチェンジの XML シリアル化に失敗しました。 UNZ の FunctionalGroup または ServiceSchema を検索しましたが、見つかりませんでした。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、TransactionSetGroup または FunctionalGroup タグがインターチェンジ XML ファイルに含まれていなかったため、送信パイプラインが保存された EDIFACT バッチ インターチェンジを処理できなかったことを示します。  
  
 BizTalk が保存されているバッチ インターチェンジを処理する場合、インターチェンジの XML ファイルで、トランザクション セットのグループまたはグループのグループに XML タグが付与されます。 グループのグループには、FunctionalGroup タグが付与されます。 ServiceSchema フラグは、保存されたバッチ インターチェンジに対して管理スキーマが使用されることを示します。 このエラー状態は、受信パイプラインとパススルー送信パイプラインを使用して、保存されたバッチを設定する場合に発生します。 タグは受信パイプラインによって設定され、送信パイプラインによって除去されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、保存されたバッチ用に生成された XML ファイルが、FunctionalGroup タグ (複数のグループ用)、ServiceSchema タグ (保存されたバッチ インターチェンジに使用される管理スキーマ用)、またはその両方を使用した整形式の XML 構造であることを確認します。