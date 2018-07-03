---
title: BatchTerminator ユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 771241fa-7df5-4882-8430-c2f36200cc9d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcbe0616f3be22a44f906ac50219584141fd6541
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995379"
---
# <a name="batchterminator-utility"></a><span data-ttu-id="99373-102">BatchTerminator ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="99373-102">BatchTerminator Utility</span></span>
<span data-ttu-id="99373-103">BatchTerminator ユーティリティを使用すると、EDI インターチェンジのバッチ処理に使用されているアクティブなバッチ処理オーケストレーションをすべて終了できます。</span><span class="sxs-lookup"><span data-stu-id="99373-103">The BatchTerminator utility enables you to terminate all live batching orchestrations being used to batch EDI interchanges.</span></span> <span data-ttu-id="99373-104">このユーティリティは、多数のバッチ処理オーケストレーション インスタンスを実行していて、BizTalk Server システムの保守を行うためにすべてのバッチを終了する必要があるときに便利です。</span><span class="sxs-lookup"><span data-stu-id="99373-104">This utility could prove useful if you have a large number of batching orchestration instances running, and you need to terminate all the batches in order to perform maintenance on the BizTalk server system.</span></span>  
  
 <span data-ttu-id="99373-105">BatchTerminator ユーティリティは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="99373-105">The BatchTerminator utility is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator folder.</span></span> <span data-ttu-id="99373-106">ユーティリティは batchterminator.log ファイルに、結果のログをバッチ処理オーケストレーション インスタンスを終了するユーティリティを実行すると、 \<*ドライブ*\>: \Documents and Settings\\<*ユーザー名*\>\Application Data フォルダー。</span><span class="sxs-lookup"><span data-stu-id="99373-106">When you run the utility to terminate the batching orchestration instances, the utility will log the results in the batchterminator.log file in the \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99373-107">BatchTerminator ユーティリティは、32 ビット システムでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="99373-107">The BatchTerminator utility is only supported on 32 bit systems.</span></span>  <span data-ttu-id="99373-108">BatchTerminator では、Microsoft.BizTalk.ExplorerOM 名前空間のコンポーネントを使用します。この名前空間は、32 ビット プロセスから使用した場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="99373-108">BatchTerminator uses components in the Microsoft.BizTalk.ExplorerOM namespace, which is only supported if used from a 32 bit process.</span></span>  
  
 <span data-ttu-id="99373-109">**終了したオーケストレーション インスタンスを再起動します。**</span><span class="sxs-lookup"><span data-stu-id="99373-109">**Restarting the Terminated Orchestration Instances**</span></span>  
  
 <span data-ttu-id="99373-110">バッチ処理オーケストレーションのグループを終了した後に、それらのオーケストレーション インスタンスをまとめて再開できます。</span><span class="sxs-lookup"><span data-stu-id="99373-110">After you terminate a group of batching orchestrations, you can do a bulk restart of those orchestration instances.</span></span> <span data-ttu-id="99373-111">そのためには、/Activate スイッチと、停止されたバッチを示すファイルの名前とパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="99373-111">You do so with the /Activate switch and the name and path of a file that indicates the batches that were stopped.</span></span> <span data-ttu-id="99373-112">この停止バッチ ファイルは、ユーティリティを実行してオーケストレーション インスタンスのグループを終了したときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="99373-112">When you run the utility to terminate a group of orchestration instances, the utility will create this stopped-batches file.</span></span> <span data-ttu-id="99373-113">停止バッチ ファイルは batchsettings-\<GUID\>で .xml、 \<*ドライブ*\>: \Documents and Settings\\<*ユーザー名* \>\Application data フォルダー。</span><span class="sxs-lookup"><span data-stu-id="99373-113">The stopped-batches file is batchSettings-\<GUID\>.xml in the \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder.</span></span> <span data-ttu-id="99373-114">ログ ファイルには、停止バッチ ファイルのパスと名前も保存されます。</span><span class="sxs-lookup"><span data-stu-id="99373-114">The path and name of the stopped-batches file is also saved in the log file.</span></span> <span data-ttu-id="99373-115">/activate スイッチを指定してユーティリティを実行すると、入力ファイルがスキーマに対して検証されます。</span><span class="sxs-lookup"><span data-stu-id="99373-115">When the utility runs with the /activate switch, it validates the input file against a schema.</span></span>  
  
 <span data-ttu-id="99373-116">**構文**</span><span class="sxs-lookup"><span data-stu-id="99373-116">**Syntax**</span></span>  
  
 <span data-ttu-id="99373-117">BatchTerminator ユーティリティは、コマンド ライン ウィンドウで次の構文を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="99373-117">Run the BatchTerminator utility in a command-line window with the following syntax:</span></span>  
  
```  
BatchTerminator /<switch>  
```  
  
 <span data-ttu-id="99373-118">BatchTerminator ユーティリティは、次のスイッチを指定して実行できます。</span><span class="sxs-lookup"><span data-stu-id="99373-118">You can run the BatchTerminator utility with the following switches.</span></span> <span data-ttu-id="99373-119">スイッチを指定しない場合、/terminate オプションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="99373-119">If no switch is provided, the /terminate option is used.</span></span> <span data-ttu-id="99373-120">下に示すように、スイッチの完全な名前 (/terminate など) または短縮形 (/t など) を入力できます。</span><span class="sxs-lookup"><span data-stu-id="99373-120">As indicate below, you can enter the full name of the switch, such as /terminate, or the shortened form, in this case, /t.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99373-121">スイッチ</span><span class="sxs-lookup"><span data-stu-id="99373-121">Switch</span></span>|<span data-ttu-id="99373-122">機能</span><span class="sxs-lookup"><span data-stu-id="99373-122">Function</span></span>|  
|<span data-ttu-id="99373-123">/?</span><span class="sxs-lookup"><span data-stu-id="99373-123">/?</span></span>|<span data-ttu-id="99373-124">ヘルプを表示します</span><span class="sxs-lookup"><span data-stu-id="99373-124">Displays help</span></span>|  
|<span data-ttu-id="99373-125">/終了 - ログ:\<*ログ ファイル*\></span><span class="sxs-lookup"><span data-stu-id="99373-125">/terminate -log:\<*log file*\></span></span><br /><br /> <span data-ttu-id="99373-126">または/t-ログ:\<*ログ ファイル*\></span><span class="sxs-lookup"><span data-stu-id="99373-126">or /t -log:\<*log file*\></span></span>|<span data-ttu-id="99373-127">すべてのアクティブな X12 または EDIFACT バッチ処理オーケストレーション インスタンスに、終了コントロール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="99373-127">Sends terminate control messages to all active X12 or EDIFACT batching orchestration instances.</span></span> <span data-ttu-id="99373-128">終了されたすべてのアクティブなバッチ オーケストレーション インスタンスの一覧、見つかったアクティブなバッチ オーケストレーションの数、および送信された終了コントロール メッセージを含む操作結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="99373-128">It displays the results of the operation, including a list of all active batch orchestration instances that it terminated, the number of active batch orchestrations that it found, and the number of terminate control messages that it sent.</span></span> <span data-ttu-id="99373-129">Batchterminator.log ファイルに結果がログに記録、 \<*ドライブ*\>: \Documents and Settings\\<*ユーザー名*\>\アプリケーション データ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="99373-129">It logs the results into the batchterminator.log file in the \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder.</span></span><br /><br /> <span data-ttu-id="99373-130">オプションの -log: パラメーターを使用すると、ログ ファイルの名前や、ログ ファイルを保存するフォルダーのパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="99373-130">The optional -log: parameter enables you to specify the name of the log file and/or the path of the folder that you want the log file to be saved to.</span></span> <span data-ttu-id="99373-131">パスとファイル名を指定するパラメーターを使用しての例は、次:`BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`します。</span><span class="sxs-lookup"><span data-stu-id="99373-131">An example of using the parameter to specify the path and file name is the following: `BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`.</span></span> <span data-ttu-id="99373-132">このパラメーターを使用してファイル名だけを指定するには、`BatchTerminator.exe /terminate -log:log.txt` のようにします。</span><span class="sxs-lookup"><span data-stu-id="99373-132">An example of using the parameter to specify the file name only is the following: `BatchTerminator.exe /terminate -log:log.txt`.</span></span> <span data-ttu-id="99373-133">ユーティリティは、既定のパスを使用して、指定されたパスが有効でない場合: \<*ドライブ*\>: \Documents and Settings\\<*ユーザー名*\>\Application データ。</span><span class="sxs-lookup"><span data-stu-id="99373-133">If the path specified is invalid, the utility will use the default path: \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data.</span></span> <span data-ttu-id="99373-134">-log: パラメーターは、/terminate スイッチを指定するかどうかにかかわらず使用できます。</span><span class="sxs-lookup"><span data-stu-id="99373-134">The -log: parameter can be used either with or without the /terminate switch.</span></span>|  
|<span data-ttu-id="99373-135">/print</span><span class="sxs-lookup"><span data-stu-id="99373-135">/print</span></span><br /><br /> <span data-ttu-id="99373-136">または /p</span><span class="sxs-lookup"><span data-stu-id="99373-136">or /p</span></span>|<span data-ttu-id="99373-137">終了コントロール メッセージを送信せずに、現在のアクティブなバッチ処理オーケストレーションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="99373-137">Displays a listing of the current active batching orchestration instances without sending terminate control messages</span></span>|  
|<span data-ttu-id="99373-138">アクティブ化/:\<*パス*\>\\</span><span class="sxs-lookup"><span data-stu-id="99373-138">/activate:\<*path*\>\\</span></span><br /><span data-ttu-id="99373-139">batchsettings-\<*GUID*\>.xml-ログ:\<*ログ ファイル*\></span><span class="sxs-lookup"><span data-stu-id="99373-139">batchSettings-\<*GUID*\>.xml -log:\<*log file*\></span></span><br /><br /> <span data-ttu-id="99373-140">または/a:\<*パス*\>\\</span><span class="sxs-lookup"><span data-stu-id="99373-140">or /a:\<*path*\>\\</span></span><br /><span data-ttu-id="99373-141">batchsettings-\<*GUID*\>.xml-ログ:\<*ログ ファイル*\></span><span class="sxs-lookup"><span data-stu-id="99373-141">batchSettings-\<*GUID*\>.xml -log:\<*log file*\></span></span>|<span data-ttu-id="99373-142">BatchSettings に記載されている以前に終了されたオーケストレーション インスタンスを再アクティブ化\<GUID\>.xml ファイルです。</span><span class="sxs-lookup"><span data-stu-id="99373-142">Reactivates the previously terminated orchestration instances that are listed in the batchSettings-\<GUID\>.xml file.</span></span> <span data-ttu-id="99373-143">入力ファイルが、コードに埋め込まれているスキーマに対して検証されます。</span><span class="sxs-lookup"><span data-stu-id="99373-143">The utility will validate the input file against a schema embedded in the code.</span></span> <span data-ttu-id="99373-144">入力ファイルがスキーマと一致しない場合、画面にエラー メッセージが出力され、プログラムが終了します。</span><span class="sxs-lookup"><span data-stu-id="99373-144">If the input file does not match the schema, an error message will be printed to the screen and the program will exit.</span></span><br /><br /> <span data-ttu-id="99373-145">-log: スイッチを指定してこの操作を実行すると、再開処理に関する情報がログ ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="99373-145">This operation writes information about the restarting action in the log file if you include the -log: switch.</span></span>|  
  
 <span data-ttu-id="99373-146">**バッチ アクティベーション ファイルの形式**</span><span class="sxs-lookup"><span data-stu-id="99373-146">**Format of the Batch Activation File**</span></span>  
  
 <span data-ttu-id="99373-147">以前の再アクティブ化を使用してバッチ オーケストレーション インスタンスを終了、/activate スイッチをバッチ アクティベーション ファイルを提供する必要があります (batchsettings-\<GUID\>.xml)。</span><span class="sxs-lookup"><span data-stu-id="99373-147">To reactivate previously terminated batch orchestration instances by using the /activate switch, you must provide a batch activation file (batchSettings-\<GUID\>.xml).</span></span> <span data-ttu-id="99373-148">このファイルは、次の形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="99373-148">This file must be in the following format:</span></span>  
  
```  
<?xml version="1.0"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" elementFormDefault="qualified" id="BatchInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="BatchTerminator">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="Batch">  
          <xs:complexType>  
            <xs:attribute name="PartyName" type="xs:string" />  
            <xs:attribute name="PartyID" type="xs:int" use="required" />  
            <xs:attribute name=”BatchName” type=”xs:string” />  
            <xs:attribute name=”BatchID” type=”xs:int” use=”required” />  
            <xs:attribute name="EdiMessageType" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="99373-149">前提条件</span><span class="sxs-lookup"><span data-stu-id="99373-149">Prerequisites</span></span>  
 <span data-ttu-id="99373-150">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99373-150">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="99373-151">BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="99373-151">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-run-the-batchterminator-utility"></a><span data-ttu-id="99373-152">BatchTerminator ユーティリティを実行するには</span><span class="sxs-lookup"><span data-stu-id="99373-152">To run the BatchTerminator utility</span></span>  
  
1. <span data-ttu-id="99373-153">Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="99373-153">In Windows Explorer, move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator folder.</span></span>  
  
2. <span data-ttu-id="99373-154">Enter **BatchTerminator**し、必要なスイッチと共にクリックして **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="99373-154">Enter **BatchTerminator**, including any desired switches, and then click **Enter**.</span></span>  
  
3. <span data-ttu-id="99373-155">Windows エクスプ ローラーで、移動\<*ドライブ*\>: \Documents and Settings\\<*ユーザー名*\>\Application Data フォルダー、および結果のログを表示する batchterminator.log ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="99373-155">In Windows Explorer, move to \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder, and open the batchterminator.log file to see a log of the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99373-156">参照</span><span class="sxs-lookup"><span data-stu-id="99373-156">See Also</span></span>  
 [<span data-ttu-id="99373-157">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="99373-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)