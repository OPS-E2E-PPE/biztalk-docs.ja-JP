---
title: 送信ポートの関連付け (AS2) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8624d4c-cee8-4072-bff7-2468d83a06de
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: babc3084515b50e0414c296f9029f223511305e3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006651"
---
# <a name="configuring-send-port-association-as2"></a>送信ポートの関連付けの構成 (AS2)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信ポートの関連付けを使用して、送信 AS2 メッセージのアグリーメントを解決します。 AS2 メッセージは、メッセージにサブスクライブした送信ポートと、アグリーメントに関連付けられた送信ポートを一致させることにより、アグリーメントに対して解決されます。 このトピックでは、送信ポートをアグリーメントと関連付ける方法について説明します。  
  
> [!IMPORTANT]
>  BizTalk Server では、送信ポートの関連付けはアグリーメント レベルでのみ行われます。 ただし、BizTalk Server 2009 で送信ポートはパーティ レベルで関連付けられました。 旧バージョンとの互換性のため、**送信ポート**ページも用意されて、パーティのプロパティの一部として (を参照してください[一般的なパーティ プロパティの構成 (AS2)](../core/configuring-general-party-properties-as2.md))。 送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。 ただし、その逆は真ではありません。 送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。  
  
> [!IMPORTANT]
>  オフにした場合に、このページで、送信ポートの関連付けグリッドが無効になって、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成中にはアグリーメント。  
>   
>  グリッドは、パーティから送信されるインターチェンジのプロパティに対応する一方向のアグリーメント タブでのみ無効になります。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、パーティ A に対しては、チェック ボックスをオフ、グリッドが無効な場合、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-send-port-association"></a>送信ポートの関連付けを構成するには  
  
1.  AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブで、をクリックして**送信ポート**です。  
  
3.  下の空のセルをクリックして、**名前**列で、ドロップダウン リストからアグリーメントと関連付ける送信ポートを選択します。 **URI**列には、送信ポートのアドレスが表示されます。  
  
4.  送信ポートの関連付けを削除する送信ポートの行を選択し、をクリックして**削除**です。  
  
5.  送信ポートのプロパティを表示する送信ポートの行を選択し、をクリックして**プロパティ**です。  
  
6.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [AS2 アグリーメントのプロパティの構成](../core/configuring-as2-agreement-properties.md)