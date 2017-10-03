---
title: "BAM 定義ファイルを管理するためのユーザー権利を必要な |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb4fb73f-b783-4a04-9bd6-a135b3dd2655
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5e39c86eec0cf198a5b879cbc98d29321de71dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="required-user-rights-for-managing-bam-definition-files"></a>BAM 定義ファイルの管理に必要なユーザー権利
BAM 定義ファイルは、どのロールのユーザーでも作成、管理、および表示を行うことができます。 BAM 定義ファイルの管理には、これらのファイルの展開と削除だけでなく、定義ファイルに関連付けられているアクティビティ、ビュー、警告、およびアイテムの管理も伴います。  
  
 管理者は、適切なアクセス許可を使用して共有フォルダーを作成するなど、適切な資産保護を維持する必要があります。 Excel の BAM アドインを使用する際は、マクロ セキュリティ レベルを高く設定することをお勧めします。  
  
 BAM 定義ファイルの変更に必要なユーザー権利はありません (定義ファイルが保存されるアクセス許可セットによって異なります)。 定義ファイルへの変更は、BAM インフラストラクチャに自動的に適用されるわけではありません。 変更を適用するには、BAM 管理ユーティリティを使用してください。  
  
 BAM 管理ユーティリティを使用するには、BAM 定義が適用されるコンピューターの管理者か、または BizTalk Server 管理者グループのメンバーである必要があります。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 定義とは何ですか。](../core/what-is-a-bam-definition.md)   
 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)