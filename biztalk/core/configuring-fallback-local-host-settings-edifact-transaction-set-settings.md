---
title: フォールバック ローカル ホスト設定の構成 (EDIFACT トランザクション セットの設定) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0142b3fc-009f-4da5-b34d-dddf4fb96e0f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caeb6c0f56a051d43596dd541a2172ff7eda2de4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391208"
---
# <a name="configuring-fallback-local-host-settings-edifact-transaction-set-settings"></a>フォールバック ローカル ホスト設定の構成 (EDIFACT トランザクション セットの設定)
受信インターチェンジを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理およびインターチェンジの検証に使用する必要があるスキーマを決定する必要があります。 多数のドキュメント、スキーマに関連付けられたターゲット名前空間の決定し、使用するスキーマを決定します。 フォールバック アグリーメントのこのページでは、ターゲット名前空間の決定に使用されるプロパティを入力します。 BizTalk Server が、スキーマを決定する方法が記載[アグリーメントの解決、スキーマ探索、および EDI メッセージの受信を承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>トランザクション セットのローカル ホスト設定を構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。  
  
2. **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**ローカル ホスト設定**します。  
  
3. 選択**末尾の区切り記号に空の XML タグを作成する**がインターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。  
  
4. 選択**小数点区切り文字として使用してドット (.)** を有効にする BizTalk Server では、10 進数を含むインターチェンジから作成された XML メッセージにドット (.) を含めます。  
  
5. **Target Namespace**、入力 (またはドロップダウン リストから選択します)、ターゲットの名前空間を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は受信メッセージを処理するスキーマを決定を使用して  
  
6. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セット設定の EDIFACT フォールバック アグリーメント プロパティの構成](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)