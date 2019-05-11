---
title: AS2 パイプラインのプロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edir2.AS2.pipeline.properties
ms.assetid: 7faf6b05-710a-4d00-8c77-590ce9d9f962
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b8168af5ba8d9fbb242833011bfb0d9a51bdd96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391353"
---
# <a name="configuring-as2-pipeline-properties"></a>AS2 パイプラインのプロパティを構成します。
パイプラインのプロパティは、受信または送信の AS2 の処理で使用メッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信または受信したインターチェンジに解決されるアグリーメントを特定することができます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
## <a name="as2-pipeline-properties"></a>AS2 パイプラインのプロパティ  
 AS2 パイプラインでは、次のプロパティを設定できます。  
  
|プロパティ|新しく使用する機能|値|パイプライン/ステージ|  
|--------------|---------|------------|---------------------|  
|ContentTransferEncoding|ASCII テキスト形式でバイナリ データを表現するメソッドが使用されることを示します。|8 bit (既定値)<br /><br /> 7 ビット<br /><br /> 8 ビット|AS2EdiSend/エンコード<br /><br /> AS2Send/エンコード|  
  
### <a name="to-set-a-pipeline-property"></a>パイプライン プロパティの設定  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、受信場所を右クリックするか送信ポートのプロパティを設定するパイプラインを使用します。 **[プロパティ]** をクリックします。  
  
2. プロパティを設定する対象のパイプラインの横にある省略記号ボタン ([…]) をクリックします。  
  
3. プロパティの値を入力し、クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server AS2 ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)