---
title: スキーマが見つかりませんでしたとしてメッセージをシリアル化できません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37897c04-650d-4695-846d-b8ba61365647
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b887d4a07d7a461278d3858289882a9ce441e9e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262674"
---
# <a name="message-cannot-be-serialized-as-the-schema-could-not-be-located"></a>スキーマが見つからなかったため、メッセージをシリアル化できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|MessageSerializationFailureDueToMissingSchema|  
|メッセージ テキスト|スキーマ {0} が見つからなかったため、メッセージをシリアル化できません。 スキーマが展開されていないか、複数のコピーが展開されています。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジのシリアル化に使用するために必要なスキーマを確認できなかったため、送信パイプラインで送信インターチェンジをシリアル化できなかったことを示します。 スキーマが展開されていないか、スキーマの複数のコピーが展開されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
1.  インターチェンジに関連付けられたスキーマが展開されていない場合は、Visual Studio を開き、BizTalk プロジェクトにスキーマを追加してから、プロジェクトをビルドして展開します。  
  
2.  スキーマの複数のコピーが展開されている場合は、Visual Studio を開き、インターチェンジに関連付けられたスキーマの 1 つを残してその他すべてを展開解除します。