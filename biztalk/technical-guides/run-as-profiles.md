---
title: 実行プロファイル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ac0a0c-91d8-4d12-aa40-2ad2e29ec784
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a51092ace594033ae559e536cb65240ac44e063
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270419"
---
# <a name="run-as-profiles"></a>実行プロファイル
BizTalk Server コア ライブラリ管理パックが最初にインポートされた 2 つの新しい実行プロファイルが作成されます。  
  
- **BizTalk Server 検出アカウント**します。 このプロファイルは、BizTalk Server ロールのコンポーネントのすべての検出に関連付けられます。  
  
- **BizTalk Server の監視アカウント**します。 このプロファイルは、すべての監視およびタスクに関連付けられています。  
  
  で、既定、すべての検出、モニター、および「既定のアクション アカウント」実行プロファイルで定義されているアカウントを使用する既定の BizTalk Server 管理パックで定義されているタスク。  特定のシステムの既定のアクション アカウントが検出または BizTalk の監視に必要なアクセス許可を持たない場合、これらのシステムは、BizTalk Server 実行プロファイルの BizTalk Server へのアクセスを持つ特定の資格情報にバインドできます。  
  
  以下は、BizTalk Server の実行プロファイルを構成する汎用的な手順です。  
  
### <a name="to-configure-run-as-profiles"></a>実行プロファイルを構成するには  
  
1.  既定のアクション アカウントが BizTalk Server を監視するのに十分な権限を持つ対象のコンピューターの名前を識別します。  
  
2.  各システムを作成または既存の BizTalk Server の権限について少なくともが資格情報のセットを使用して、[低い特権の環境](../technical-guides/low-privilege-environments.md)この管理パック ガイドの「します。  
  
3.  手順 2. で識別した資格情報のセットごとに、対応する実行アカウントが、管理グループに存在するを確認します。 必要がある場合は、実行アカウントを作成します。  
  
4.  ターゲットと実行アカウントは、間のマッピングを設定、**アカウントとして実行**実行プロファイルのそれぞれのタブ。