---
title: ISA セグメントは、108 の最小の長さである必要があります |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57641445-cebb-4219-998d-54038d7ddf19
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d511e0a50d610313bbe1c7ce4b3137c55ad0328
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329685"
---
# <a name="isa-segment-needs-to-have-a-minimum-length-of-108"></a>ISA セグメントは、108 の最小の長さである必要があります。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                               NseIsaSuffix1LFDescription                               |
|  メッセージ テキスト   |          ISA セグメントは、108 の最小の長さである必要があります、インスタンスには {0}           |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジの ISA セグメントがサービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定された桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ISA セグメント (ISA01 から ISA16 まで) の各フィールドに必要な最小桁数が含まれていることを確認します。 最小桁数を確認するには、BizTalk Server 管理コンソールを開き、[BizTalk グループ] ノードを開きます。次に、[アプリケーション] ノード、[BizTalk EDI アプリケーション] ノード、スキーマ ノードの順に開き、ISA のルート ノードで Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema を開いて、[スキーマ ビュー] をクリックします。