---
title: 状態レポートを有効にするには実行&#39;BizTalk Server 構成&#39;および EDI AS2 状態レポート機能の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf125919-80ab-4cb8-b1f5-0f2616cc6f5c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89d7fcf5e473485d0b61edcd6d5f287198021d3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992715"
---
# <a name="to-enable-status-reporting-run-39biztalk-server-configuration39-and-configure-edi-as2-status-reporting-feature"></a>状態レポートを有効にするには実行&#39;BizTalk Server 構成&#39;および EDI AS2 状態レポート機能の構成
## <a name="details"></a>詳細  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  製品名   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| 製品バージョン |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    イベント ID     |                                                       -                                                        |
|  イベント ソース   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI             |
|    コンポーネント    |                                                   EDI エンジン                                                   |
|  シンボル名  |                                                       0                                                        |
|  メッセージ テキスト   | 状態レポートを有効にするには、'BizTalk Server 構成' を実行し、EDI/AS2 状態レポート機能を構成してください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI/AS2 状態レポートが構成されていないため、レポートが動作していないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
1.  BizTalk Server 構成ウィザードを実行します。 [BizTalk EDI/AS2 ランタイム] ノードをクリックし、[この BizTalk グループの BizTalk EDI/AS2 ランタイム状態レポートを有効にする] プロパティをオンにします。 EDI/AS2 状態レポートを構成するには、BAM を構成する必要があります。  
  
2.  BizTalk Server 管理コンソールで、[EDI のプロパティ] ダイアログ ボックスの [全般] ページの [EDI レポートをアクティブにする] プロパティをクリックして、パーティの EDI 状態レポートを有効にします。 [AS2 のプロパティ] ダイアログ ボックスの [全般] ページの [AS レポートをアクティブにする] プロパティをクリックして、パーティの AS2 状態レポートを有効にします。 EDI または AS2 状態レポートを有効にした後に、BizTalk サービスを再起動する必要があります。