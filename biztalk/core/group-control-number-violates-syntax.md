---
title: グループ制御番号が構文に違反しています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e173c914-cb5c-4369-ac2f-8f9abee420cb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7664a85d0cb1bb0c83ef53c6c584c51b532d6c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344880"
---
# <a name="group-control-number-violates-syntax"></a>グループ制御番号が構文に違反しています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                          X12FaInvalidControlNumberDescription                          |
|  メッセージ テキスト   |                          グループ制御番号が構文に違反しています                          |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジの GS06 および GE02 フィールドのグループ制御番号が、サービス スキーマで指定されたデータ型または長さに準拠していなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。 サービス スキーマは BaseArtifacts.dll 内の X12ServiceSchema です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの GS06 および GE02 フィールドに含まれているグループ制御番号が、サービス スキーマに指定されているデータ型 (X12_N0) および長さ (1 ～ 9 桁) に準拠していることを確認して、インターチェンジを再送信してもらいます。