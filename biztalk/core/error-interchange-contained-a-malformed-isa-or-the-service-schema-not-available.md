---
title: インターチェンジに正しくない形式の ISA が含まれているか、サービス スキーマが利用できなかった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d285f6-26fb-4a3b-a959-a17623321b20
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce469b25a2ba15c3038ea9079c3f22fc4f8c0c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010715"
---
# <a name="the-interchange-contained-a-malformed-isa-or-the-service-schema-was-not-available"></a>インターチェンジに正しくない形式の ISA が含まれていたか、サービス スキーマを使用できませんでした
## <a name="details"></a>詳細  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  製品名   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 製品バージョン |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    イベント ID     |                                                         -                                                          |
|  イベント ソース   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI               |
|    コンポーネント    |                                                     EDI エンジン                                                     |
|  シンボル名  |                                                 MalformedIsaError                                                  |
|  メッセージ テキスト   | インターチェンジに正しくない形式の ISA が含まれていたかサービス スキーマを使用できなかったため、このインターチェンジ全体が拒否されています |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジの ISA または IEA セグメントが X12ServiceSchema に準拠していなかったか、または (BaseArtifacts.dll 内の) X12ServiceSchema が展開されなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   インターチェンジの送信者に対して、ISA および IEA セグメントを変更し、X12ServiceSchema に準拠させるように依頼します。  
  
-   BaseArtifacts.dll に X12ServiceSchema が含まれていることと、X12ServiceSchema が展開されることを確認します。 そのためには、BizTalk Server 管理コンソールを開き、[BizTalk EDI アプリケーション] ノードの [スキーマ] ノードを開いて、X12ServiceSchema が表示されていることを確認します。