---
title: "実行プロファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ac0a0c-91d8-4d12-aa40-2ad2e29ec784
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69fa6c9401f606619b2fb8d22d95ded48c18a092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-as-profiles"></a>実行プロファイル
BizTalk Server コア ライブラリ管理パックが最初にインポートされると、2 つの新しい実行プロファイルが作成されます。  
  
-   **BizTalk Server 検出アカウント**です。 このプロファイルは、BizTalk Server ロール コンポーネントのすべての検出に関連付けられます。  
  
-   **BizTalk Server 監視アカウント**です。 このプロファイルは、すべての監視およびタスクに関連付けられています。  
  
 既定ですべての検出、モニター、や「既定のアクション アカウント」実行プロファイルで定義されているアカウントを使用する既定の BizTalk Server 管理パックで定義されているタスクです。  指定したシステムの既定のアクション アカウントが検出または BizTalk の監視に必要なアクセス許可を持たない場合、これらのシステムは、BizTalk Server 実行プロファイルに、BizTalk Server へのアクセスを持つ特定の資格情報をバインドできます。  
  
 BizTalk Server の実行プロファイルを構成する汎用的な手順を次に示します。  
  
### <a name="to-configure-run-as-profiles"></a>実行プロファイルを構成するには  
  
1.  既定のアクション アカウントが BizTalk Server の監視に必要な権限を持つ、対象コンピューターの名前を識別します。  
  
2.  各システムを作成または既存の特権を持つには、少なくとも、BizTalk Server で説明されている資格情報のセットを使用して、[低い特権の環境](../technical-guides/low-privilege-environments.md)この管理パック ガイドの「します。  
  
3.  手順 2. で識別した資格情報のセットごとに、管理グループ内に対応する実行アカウントが存在することを確認します。 必要がある場合は、実行アカウントを作成します。  
  
4.  ターゲットと実行アカウントのマッピングを設定、**アカウントとして実行**の実行プロファイルは、それぞれのタブです。