---
title: "フォールバック ローカル ホスト設定の構成 (EDIFACT トランザクション セットの設定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0142b3fc-009f-4da5-b34d-dddf4fb96e0f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931db62edda264a6fff0ddb422bd41b243cd29ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-local-host-settings-edifact-transaction-set-settings"></a>フォールバック ローカル ホスト設定の構成 (EDIFACT トランザクション セットの設定)
受信したインターチェンジを処理するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジの処理および検証に使用するスキーマを決定する必要があります。 この場合、スキーマに関連付けられたターゲット名前空間および使用するスキーマを決定します。 フォールバック アグリーメントに関するこのページで、ターゲットの名前空間の決定に使用するプロパティを入力します。 BizTalk Server が、スキーマを決定する方法が説明されている[アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>トランザクション セットのローカル ホスト設定を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**パーティ**ノードをクリックして**EDIFACT フォールバックの設定**です。  
  
2.  **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**ローカル ホスト設定**です。  
  
3.  選択**末尾の区切り記号に空の XML タグを作成して**末尾の区切り記号に空の XML タグを含めるインターチェンジの送信者にします。  
  
4.  選択**小数点区切り文字として使用してドット (.)**できるようにする BizTalk Server では、10 進数を含むインターチェンジから作成された XML メッセージにドット (.) を含めます。  
  
5.  **Target Namespace**、入力 (またはドロップダウン リストから選択) ターゲットの名前空間を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で受信したメッセージを処理するスキーマを決定に使用されます  
  
6.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクションの EDIFACT フォールバック アグリーメント プロパティの構成設定](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)