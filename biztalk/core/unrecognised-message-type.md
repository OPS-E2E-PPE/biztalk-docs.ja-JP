---
title: 認識できないメッセージの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4094bf-af00-4d5c-9661-7c8abcb1b722
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd58907b61e68140ccf68d8256882b81e46bd863
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286802"
---
# <a name="unrecognised-message-type"></a>メッセージの種類が認識されていません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|UnRecognizedMessageType|  
|メッセージ テキスト|メッセージの種類が認識されていません。 続行できません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、対象のインターチェンジにおいてトランザクション セットのドキュメントの種類に応じたドキュメント スキーマが展開されていないか、または BizTalk Server が、トランザクション セットの識別子コード、バージョン、および名前空間からドキュメントの種類を判別できないため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   インターチェンジのトランザクション セットのドキュメントの種類に応じたドキュメント スキーマを展開し、インターチェンジを再送信します。  
  
-   次の値が有効なスキーマを定義することを確認してください: x12 の場合、ターゲットの名前空間、バージョン/リリース、およびドキュメントを入力します。edifact の場合、ターゲットの名前空間、メッセージのバージョン番号、メッセージのリリース番号、およびメッセージを入力します。 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの「受信した EDI メッセージのパーティの解決、スキーマ探索、および認証」トピックで、「スキーマ探索」を参照してください。