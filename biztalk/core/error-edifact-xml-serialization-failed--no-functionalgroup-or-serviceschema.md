---
title: "無効な構造体、FunctionalGroup または ServiceSchema はないため Edifact インターチェンジの Xml シリアル化に失敗しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 530faadd-e301-4743-b4b3-b04ba7578f1d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f79d64a9ec19e62f13220be056335bf2d249519a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-functionalgroup-or-serviceschema"></a>無効な構造により、EDIFACT インターチェンジの XML シリアル化に失敗しました。FunctionalGroup または ServiceSchema はありません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|無効な構造により、EDIFACT インターチェンジの XML シリアル化に失敗しました。 UNZ の FunctionalGroup または ServiceSchema を検索しましたが、見つかりませんでした。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、TransactionSetGroup または FunctionalGroup タグがインターチェンジ XML ファイルに含まれていなかったため、送信パイプラインが保存された EDIFACT バッチ インターチェンジを処理できなかったことを示します。  
  
 BizTalk が保存されているバッチ インターチェンジを処理する場合、インターチェンジの XML ファイルで、トランザクション セットのグループまたはグループのグループに XML タグが付与されます。 グループのグループには、FunctionalGroup タグが付与されます。 ServiceSchema フラグは、保存されたバッチ インターチェンジに対して管理スキーマが使用されることを示します。 このエラー状態は、受信パイプラインとパススルー送信パイプラインを使用して、保存されたバッチを設定する場合に発生します。 タグは受信パイプラインによって設定され、送信パイプラインによって除去されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、保存されたバッチ用に生成された XML ファイルが、FunctionalGroup タグ (複数のグループ用)、ServiceSchema タグ (保存されたバッチ インターチェンジに使用される管理スキーマ用)、またはその両方を使用した整形式の XML 構造であることを確認します。