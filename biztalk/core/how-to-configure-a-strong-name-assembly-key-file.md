---
title: 厳密な名前のアセンブリ キー ファイルを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5778a8ec-f5f7-4ae1-a57e-99f6503f044c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c98ad06e902d06f2d24ac5f6fb01a2228753795
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006795"
---
# <a name="how-to-configure-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリ キー ファイルを構成する方法
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] では、BizTalk ソリューションを展開するプロセスで、まずアセンブリのビルドが行われます。 このとき各アセンブリは、厳密に署名されている必要があります。 プロジェクトに厳密な名前のアセンブリ キー ファイルを関連付けることによって、アセンブリを厳密に署名できます。 まだ行っていない場合は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からソリューションを展開する前に、次の手順に従って、厳密な名前のアセンブリ キー ファイルを生成し、ソリューション内の各プロジェクトに割り当ててください。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーであるアカウントを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者のグループ。 また、使用するアカウントには、グローバル アセンブリ キャッシュ (GAC) に対する書き込みアクセス許可が必要です。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  
  
### <a name="to-configure-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリ キー ファイルを構成するには  
  
1. 開始**Visual Studio コマンド プロンプト**します。  
  
2. コマンド プロンプトで、キー ファイルを格納するフォルダーから次のコマンドを入力し、Enter キーを押します。  
  
    **sn/k***file_name* **.snk**   
  
    例: **sn/k ErrorHandling.snk**  
  
    確認メッセージ、**キーのペアに書き込まれる** \< *file_name*\>**.snk** `,`コマンド ラインで表示されます。  
  
3. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでプロジェクトを右クリックし、順にクリックします**プロパティ**します。  
  
4. をクリックして、**署名**タブおよび選択**参照**で、**厳密な名前キー ファイルを選択して**ボックスの一覧します。  
  
5. キー ファイルを参照してクリックします。 クリックして**オープン**、プロジェクトのプロパティを閉じます。  
  
6. この厳密な名前のアセンブリ キー ファイルを使用して展開するソリューション内のプロジェクトごとに、手順 3. ～ 6. を繰り返します。  
  
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)