---
title: マップのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 265afd62-3c1d-4b9a-9f51-176b9b079241
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ad35dd513375f8221ed909fd7f353fc5e6673c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983939"
---
# <a name="testing-a-map"></a>マップのテスト
デザイン時に EDI プロジェクトのマップをテストできます。 それには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の XML ツール拡張を使用します。 このトピックでは、設定して使用する方法を説明します、**マップのテスト**XML ツール拡張の機能です。  
  
 送信元ドキュメントを指定し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が (架空のデータを使用して) 生成したインスタンスを保存するフォルダーを指定して、マップをテストします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が送信元ドキュメントを処理し、EDI スキーマに従って送信先ドキュメントを生成するのに使用する、区切り記号を設定する必要があります。 これは、すべての値は true、 **TestMap**マップのプロパティ ページでプロパティを入力:**インスタンスの生成**、 **XML**、または**ネイティブ**します。 True に設定**インスタンスの生成**ため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にどのような区切り記号を使用して、インスタンスを生成する必要があります。 True に設定**XML**または**ネイティブ**ため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ネイティブのフラット ファイルまたは XML ファイルを解釈する方法を理解する必要があります。 さらに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が出力ファイルを生成するときに使用する区切り記号も設定する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-test-a-map"></a>マップをテストするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、テストするマップをプロジェクトに追加し、そのマップの送信元スキーマおよび送信先スキーマをプロジェクトに追加します。  
  
   > [!NOTE]
   >  マップをテストするプロジェクトをビルドする必要はありません。  
  
2. マップを右クリックし、をクリックして**プロパティ**します。  
  
3. **プロパティ**ウィンドウで、設定**TestMap 入力の検証**に**True**送信元スキーマに対して入力ファイルを検証する場合。 設定**TestMap 出力の検証**に**True**送信先スキーマを出力ファイルを検証する場合。  
  
   > [!NOTE]
   >  使用してマップをテストする場合、 **TestMap の入力**プロパティに設定**ネイティブ**と**TestMap 入力の検証**と**TestMap 出力の検証**プロパティを設定**False**検証は実行されます。 これは、ネイティブ形式の入力ファイルが XML 形式に変換され、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が XML をスキーマに対して検証するためです。 検証メカニズムによってエラーが通知される場合でも入力インスタンスに検証の問題がある場合、 **TestMap 入力の検証**と**TestMap 出力の検証**にプロパティが設定されて**False**します。  
  
4. 設定**TestMap の入力**に**ネイティブ**.edi 拡張子を持つ入力ファイルです。 設定**XML** .xml 拡張子がある場合。 設定**TestMap の入力**に**インスタンスの生成**が[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]入力インスタンスを手動で指定することではなく、入力のインスタンスを生成します。  
  
5. 設定**TestMap 出力**に**ネイティブ**.edi 拡張子を持つ出力ファイル。 設定**XML** .xml 拡張子がある場合。  
  
6. **TestMap の入力インスタンス**、マップをテストして、それを選択するために使用する入力インスタンスに移動し、**オープン**します。 このプロパティを空白のままにする場合は、設定**TestMap の入力**に**インスタンスの生成**します。  
  
   > [!NOTE]
   >  いずれかの入力インスタンスを指定する必要が**TestMap の入力インスタンス**設定または**TestMap の入力**に**インスタンスの生成**します。 設定されていないと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが発生します。  
  
7. **TestMap 出力インスタンス**、参照を保存する出力インスタンスの出力インスタンスの名前を入力し、をクリックする場所に**保存**します。  
  
   > [!NOTE]
   >  出力インスタンスを指定しないと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が出力ファイルを作成し、フォルダーに出力ファイルを格納して、ファイル名とパスを示します。  
  
8. テストをクリックしたマップを右クリックして**マップのテスト**します。  
  
9. X12 で**EDI インスタンスのプロパティ** ダイアログ ボックスで、すべてのプロパティが入力と出力インスタンスの設定に整合性があることを確認します。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 表示されます、 **EDI インスタンスのプロパティ**TestMap プロセス中に 2 回のダイアログ ボックス: 入力メッセージ インスタンスの解釈で 1 回は出力メッセージ インスタンスを生成するためです。 ただし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はダイアログ ボックスを 3 回以上表示したり、EDI スキーマ以外のダイアログ ボックスを表示したりすることがあります。 そうである場合にクリックします**OK**ダイアログ ボックスを閉じます。  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [デザイン時 XML ツールを使用します。](../core/using-design-time-xml-tools.md)