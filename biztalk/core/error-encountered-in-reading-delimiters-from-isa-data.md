---
title: ISA データから区切り記号を読み取り中に発生したエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cb60abd-53c8-45e1-a840-d27dc974aad7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e99412ee1d0048aa3d7d6db373d20fe9af0ac57e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348491"
---
# <a name="error-encountered-in-reading-delimiters-from-isa-data"></a>ISA データから区切り記号を読み取り中にエラーが発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                     InvalidIsaData                                     |
|  メッセージ テキスト   |                 ISA データから区切り記号を読み取り中にエラーが発生しました                  |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ISA セグメントからの区切り記号を解析できなかったため、受信 X12 インターチェンジの処理中に EDI 受信パイプラインでエラーが発生したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、受信インターチェンジの ISA セグメントの区切り記号が一意で有効であることを確認します。 そうでない場合は、インターチェンジの送信者に対して、区切り記号の各フィールド (繰り返し区切り記号の場合は ISA11 セグメント、コンポーネント区切り記号の場合は ISA16 セグメント) に一意で有効な値を入力してから、インターチェンジを再送信するように依頼します。