---
title: フォールバック ローカル ホスト設定 (X12 トランザクション セットの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68511199-a7ed-45b3-807d-70378b2c6ebb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3eb3ed007a30e2d65c4d65aebe98ebabf2f93c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391215"
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a>フォールバック ローカル ホスト設定の構成 (X12 トランザクションセットの設定)
受信インターチェンジを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理およびインターチェンジの検証に使用する必要があるスキーマを決定する必要があります。 多数のドキュメント、スキーマに関連付けられたターゲット名前空間の決定し、使用するスキーマを決定します。 フォールバック アグリーメントのこのページでは、フォールバック ターゲットの名前空間を指定します。 どの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]決定スキーマについては、「[アグリーメントの解決、スキーマ探索、および EDI メッセージの受信を承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)します。  
  
> [!NOTE]
>  このトピックでは、HIPAA 関連の設定にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>トランザクション セットのローカル ホスト設定を構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。  
  
2. **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**ローカル ホストの設定**.  
  
3. 選択**変換には 10 進形式 Nn を底 10 の数値が含まれる**を BizTalk Server での中間 XML で底 10 の数値形式 Nn で指定されている EDI 番号を変換します。  
  
   > [!NOTE]
   >  この変換後の中間 XML に長さの検証は失敗します。 これは、底 10 の数値書式の数値は、Nn 形式で、長さ、数より大きい値のいずれかを行う、10 進数を含まれているために発生します。 値を追加することで、この問題を解決できます**1**最小値/最大長の値にします。  
  
4. 選択**末尾の区切り記号に空の XML タグを作成する**がインターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。  
  
5. **Target Namespace**、入力 (またはドロップダウン リストから選択します)、ターゲットの名前空間を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、受信メッセージを処理するスキーマを決定します。  
  
6. をクリックして**適用**を変更を受け入れるか、をクリックする**OK**を入力し、変更を検証して、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セットの設定の X12 フォールバック アグリーメント プロパティの構成](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)