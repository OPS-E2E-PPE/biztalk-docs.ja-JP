---
title: 機能グループのバージョンがサポートされていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715e6585-a07a-4060-a15b-0c9603fbef19
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cae2be8619f07de4d0f1178c308b332165b5954e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387809"
---
# <a name="functional-group-version-not-supported"></a>機能グループのバージョンがサポートされていません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                        X12FaGroupVersionNotSupportedDescription                        |
|  メッセージ テキスト   |                         機能グループのバージョンがサポートされていません                         |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が、機能グループのセグメント GS08 のバージョン番号をサポートしていないため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのすべての機能グループのセグメント GS08 の各インスタンスのバージョン番号が BizTalk Server でサポートされていることを確認してから、インターチェンジを再送信してもらいます。 BizTalk Server がサポートしている標準バージョンは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 製品ヘルプの「EDI ドキュメント スキーマのサポート」トピックに記載されています。