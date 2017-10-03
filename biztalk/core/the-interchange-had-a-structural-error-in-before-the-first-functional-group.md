---
title: "インターチェンジ構造エラーが、最初の機能グループの前に |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12202148-0a32-464e-8dbd-d01b9ba530eb
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d5ab490de214f53e85ea32c1b243456f837c72e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-interchange-had-a-structural-error-in-before-the-first-functional-group"></a>インターチェンジ構造エラーが、最初の機能グループの前に
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12InterchangeStructuralErrorBefore1stGroup|  
|メッセージ テキスト|Id '{0}'、送信者 id '{1}' で、インターチェンジ受信者 id '{2}' が最初の機能グループ内/前に、の構造のエラー|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、次のいずれかの理由により、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
-   インターチェンジの ISA セグメントと IEA セグメントまたは最初の機能グループで構造エラーが発生しました。インターチェンジが該当するスキーマに準拠していません。  
  
-   (BaseArtifacts.dll 内の) X12ServiceSchema が展開されていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   ISA セグメント、IEA セグメント、またはその両方のセグメントか最初の機能グループを、該当するスキーマに準拠するようにインターチェンジの送信者に変更してもらい、インターチェンジを再送信します。  
  
-   BaseArtifacts.dll に X12ServiceSchema が含まれていることと、X12ServiceSchema が展開されることを確認します。 これを行うには、BizTalk Server 管理コンソールを開き、[BizTalk EDI アプリケーション] ノードの [スキーマ] ノードを開いて、X12ServiceSchema が表示されていることを確認します。