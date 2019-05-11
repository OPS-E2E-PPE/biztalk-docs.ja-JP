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
ms.openlocfilehash: ce4dad74ae2b01684d7bd0650d8e1887af456e74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386933"
---
# <a name="how-to-configure-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリ キー ファイルを構成する方法
BizTalk ソリューションをデプロイ中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]最初に、アセンブリをビルドします。 展開プロセスでは、各アセンブリが厳密に署名されている必要があります。 プロジェクトに厳密な名前のアセンブリ キー ファイルを関連付けることによって、アセンブリを厳密に署名できます。 かどうかをまだ行っていないからソリューションをデプロイする前に[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、次の手順を使用して、厳密な名前のアセンブリ キー ファイルを生成し、ソリューション内の各プロジェクトに割り当てます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーであるアカウントを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者のグループ。 さらに、自分のアカウントでは、グローバル アセンブリ キャッシュ (GAC) に書き込みアクセス許可が必要です。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  
  
### <a name="to-configure-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリ キー ファイルを構成するには  
  
1. 開始**Visual Studio コマンド プロンプト**します。  
  
2. コマンド プロンプトで、キー ファイルを格納するフォルダーから次のコマンドを入力し、Enter キーを押します。  
  
    **sn /k**  *file_name* **.snk**  
  
    例: **sn/k ErrorHandling.snk**  
  
    確認メッセージ、**キーのペアに書き込まれる** \< *file_name*\>**.snk** `,`コマンド ラインで表示されます。  
  
3. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでプロジェクトを右クリックし、順にクリックします**プロパティ**します。  
  
4. をクリックして、**署名**タブおよび選択**参照**で、**厳密な名前キー ファイルを選択して**ボックスの一覧します。  
  
5. キー ファイルを参照し、それをクリックします。 クリックして**オープン**、プロジェクトのプロパティを閉じます。  
  
6. この厳密な名前のアセンブリ キー ファイルを使用してデプロイするソリューション内の各プロジェクトには、手順 3. 6. からを繰り返します。  
  
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)