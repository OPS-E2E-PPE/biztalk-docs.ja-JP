---
title: ファイル アダプタ構成時の制限事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], restrictions
- File adapters, restrictions
ms.assetid: 8d8137a7-5b16-4ae3-a0a7-6d114324bdf3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6fbf9296e56db816277f9a7a348377bfa4b359d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975134"
---
# <a name="restrictions-when-configuring-the-file-adapter"></a><span data-ttu-id="3a743-102">ファイル アダプタ構成時の制限事項</span><span class="sxs-lookup"><span data-stu-id="3a743-102">Restrictions when configuring the File adapter</span></span>
<span data-ttu-id="3a743-103">制限と、ファイル アダプターを使用する場合の規則。</span><span class="sxs-lookup"><span data-stu-id="3a743-103">Restrictions and rules when using the file adapter.</span></span>

## <a name="file-mask-and-file-name-gotchas"></a><span data-ttu-id="3a743-104">ファイル マスクおよびファイル名の潜在的な問題</span><span class="sxs-lookup"><span data-stu-id="3a743-104">File mask and file name gotchas</span></span>

<span data-ttu-id="3a743-105">ファイル マスクは、ファイル受信ハンドラが受信場所から取得するファイルの種類を指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="3a743-105">The file mask is a string that specifies the type of file that the File receive handler will pick up from the receive location.</span></span> <span data-ttu-id="3a743-106">ファイル名は、ファイル送信ハンドラがメッセージを書き込むファイルの名前を指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="3a743-106">The file name is a string that specifies the name of the file where the File send handler will write the message.</span></span>  
  
 <span data-ttu-id="3a743-107">ファイル名およびファイル マスクのプロパティには、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a743-107">The following restrictions apply to the file name and file mask properties:</span></span>  
  
-   <span data-ttu-id="3a743-108">各受信場所または送信ポートに指定できるファイル マスクまたはファイル名は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="3a743-108">Only one file mask or file name can be specified per receive location or send port.</span></span>  
  
-   <span data-ttu-id="3a743-109">ファイル マスクまたはファイル名と共に完全パスまたはパスの一部を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a743-109">The full path or part of the path along with the file mask or file name is not allowed.</span></span> <span data-ttu-id="3a743-110">ファイル マスクおよびファイル名は、常にパスを除いた名前を表します。</span><span class="sxs-lookup"><span data-stu-id="3a743-110">The file mask and file name always represent a name without the path.</span></span>  
  
-   <span data-ttu-id="3a743-111">ファイル マスクとファイル名では、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="3a743-111">The file mask and file name are not case-sensitive.</span></span>  
  
-   <span data-ttu-id="3a743-112">ファイル名には、次の文字を含めることはできません: \< \> :/&#124;です。" ?</span><span class="sxs-lookup"><span data-stu-id="3a743-112">The file name cannot contain any of the following characters: \< \> : / &#124; " ?</span></span> <span data-ttu-id="3a743-113">\* ;</span><span class="sxs-lookup"><span data-stu-id="3a743-113">\* ;</span></span>  
  
-   <span data-ttu-id="3a743-114">ファイル マスクには、次の文字を含めることはできません: \< \> :/&#124;です。" ;</span><span class="sxs-lookup"><span data-stu-id="3a743-114">The file mask cannot contain any of the following characters: \< \> : / &#124; " ;</span></span> 
  
-   <span data-ttu-id="3a743-115">予約されたデバイス名 (CON、PRN、AUX、CLOCK$、NUL、COM1、COM2、COM3、COM4、COM5、COM6、COM7、COM8、COM9、LPT1、LPT2、LPT3、LPT4、LPT5、LPT6、LPT7、LPT8、および LPT9) は、ファイル名として使用できません。</span><span class="sxs-lookup"><span data-stu-id="3a743-115">The following reserved device names cannot be used as the name of a file: CON, PRN, AUX, CLOCK$, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, and LPT9.</span></span> <span data-ttu-id="3a743-116">また、これらの名前を拡張子と組み合わせて使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a743-116">In addition, any combinations of these with extensions are not allowed.</span></span>  
  
-   <span data-ttu-id="3a743-117">Windows ディスク ボリュームは、既定では、短期および長期のファイル名を使用する名前付け規則 8.3 (8dot3) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a743-117">Windows disk volumes use the 8.3 (8dot3) naming convention by default, which uses short and long file names.</span></span> <span data-ttu-id="3a743-118">非システムのディスク ボリュームは 8dot3 名前付け規則を無効にし、したがってのみ長いファイル名を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a743-118">Non-system disk volumes disable the 8dot3 naming convention, and therefore only use long file names.</span></span> 

    <span data-ttu-id="3a743-119">8dot3 を有効にすると、ファイルとファイル拡張子の短い名前に変換します。</span><span class="sxs-lookup"><span data-stu-id="3a743-119">When 8dot3 is enabled, files and their file extensions get converted to a short name.</span></span> <span data-ttu-id="3a743-120">たとえば、`testabcdefgh.docx`に変換を取得`testab~1.doc`です。</span><span class="sxs-lookup"><span data-stu-id="3a743-120">For example, `testabcdefgh.docx` gets converted to `testab~1.doc`.</span></span> <span data-ttu-id="3a743-121">ファイル名を短くと、しから、ファイル拡張子の部分が切り捨てられたことに注意してください`.docx`に`doc`です。</span><span class="sxs-lookup"><span data-stu-id="3a743-121">Notice that file name is shortened, and the file extension is shortened from `.docx` to `doc`.</span></span>

    <span data-ttu-id="3a743-122">この動作は、ファイル アダプターがファイルを受け取る方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="3a743-122">This behavior impacts how the File adapter receives file.</span></span> <span data-ttu-id="3a743-123">ファイル マスクに設定されている場合`*.xml`、し、ファイルの両方に一致する`*.xml`と`*.xmln`拡張機能が選択されています。</span><span class="sxs-lookup"><span data-stu-id="3a743-123">If a file mask is set to `*.xml`, then files matching both `*.xml` and `*.xmln` extensions are picked up.</span></span> 

    <span data-ttu-id="3a743-124">表示、ディスク上 8dot3 名前付け規則が有効になっているかどうかは、管理者、および型としてコマンド プロンプトを開き`fsutil 8dot3name query c:`、または`fsutil 8dot3name query d:`のようにします。</span><span class="sxs-lookup"><span data-stu-id="3a743-124">To see if the 8dot3 naming convention is enabled on your disks, open a command prompt as Administrator, and type `fsutil 8dot3name query c:`, or `fsutil 8dot3name query d:`, and so on.</span></span> <span data-ttu-id="3a743-125">サンプル出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3a743-125">Sample output looks like the following:</span></span>

    ```
    C:\WINDOWS\system32>fsutil 8dot3name query c:
    The volume state is: 0 (8dot3 name creation is enabled).
    The registry state is: 2 (Per volume setting - the default).
    
    Based on the above two settings, 8dot3 name creation is enabled on c:
    ```
    
    <span data-ttu-id="3a743-126">ファイル アダプターを使用して、 [FindFirstFile 関数](https://msdn.microsoft.com/library/windows/desktop/aa364418(v=vs.85).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="3a743-126">The File adapter uses the [FindFirstFile function](https://msdn.microsoft.com/library/windows/desktop/aa364418(v=vs.85).aspx).</span></span> <span data-ttu-id="3a743-127">この関数には、短期および長期のファイルの名前を持つ検索結果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a743-127">This function includes search results that have the short and long file names.</span></span> <span data-ttu-id="3a743-128">フォルダーで、短期および長期のファイル名を表示するには、コマンド プロンプトを開き、フォルダー、種類にアクセスして、`dir /x`です。</span><span class="sxs-lookup"><span data-stu-id="3a743-128">To see the short and long file names in a folder, open a command prompt, go to your folder, and type `dir /x`.</span></span> <span data-ttu-id="3a743-129">コマンド プロンプトで入力することも`dir c:\foldername /x`します。</span><span class="sxs-lookup"><span data-stu-id="3a743-129">In a command prompt, you can also type `dir c:\foldername /x`.</span></span>
    
    <span data-ttu-id="3a743-130">ボリュームに 8dot3name 設定を変更する場合、新しいファイルでは、新しい設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a743-130">If you change the 8dot3name setting on a volume, then new files use the new setting.</span></span> <span data-ttu-id="3a743-131">既存のファイルは、それらも移動するまでに、名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="3a743-131">Any existing files keep their names until they are moved.</span></span> 
    
    <span data-ttu-id="3a743-132">のみを目的のファイルを選択して、負荷が高い中にパフォーマンスの向上 (オーバーヘッドが少ない) を取得するには、しがありますに 8dot3name が無効になっているボリュームを使用する、ファイル アダプターを設定してください。</span><span class="sxs-lookup"><span data-stu-id="3a743-132">To only pick up your intended files, and to get better performance (less overhead) during higher load, then it may be best to configure the File adapter to use a volume where 8dot3name is disabled.</span></span> 
  
-   <span data-ttu-id="3a743-133">ファイル パス、ファイル マスク、およびファイル名の長さの合計 (マクロによる代入を除く) は 256 文字以下にしてください</span><span class="sxs-lookup"><span data-stu-id="3a743-133">The total length of the file path, file mask, and file name (without macro substitution) must not exceed 256 characters.</span></span> <span data-ttu-id="3a743-134">(これは、メッセージ ボックス データベースの制限です)。</span><span class="sxs-lookup"><span data-stu-id="3a743-134">(This is a restriction of the MessageBox database.)</span></span>  
  
-   <span data-ttu-id="3a743-135">ファイル パスを "`\\`?" で始めることはできません。</span><span class="sxs-lookup"><span data-stu-id="3a743-135">The file path cannot begin with "`\\`?".</span></span>  
  
-   <span data-ttu-id="3a743-136">割り当てられたネットワーク ドライブ名は、ユーザー セッションに基づいているため、ファイル パスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3a743-136">Mapped network drive letters cannot be used in the file path, because they are user session based.</span></span>  
  
 <span data-ttu-id="3a743-137">BizTalk メッセージング エンジンでは、上記の項目を使用して、デザイン時に常にファイル名およびファイル マスクのプロパティを検証します。</span><span class="sxs-lookup"><span data-stu-id="3a743-137">The BizTalk Messaging Engine always validates the file name and file mask properties at design time by using the items previously listed.</span></span> <span data-ttu-id="3a743-138">また、ファイル アダプタでは、アダプタが動的ポートでメッセージを送信する場合、実行時にファイル名およびファイル マスクのプロパティを検証します。</span><span class="sxs-lookup"><span data-stu-id="3a743-138">In addition, the File adapter validates the file name and file mask properties at run time if the adapter sends the message on a dynamic port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a743-139">ファイル アダプタでは、システム ファイルまたは読み取り専用のファイルは取得されません。</span><span class="sxs-lookup"><span data-stu-id="3a743-139">The File adapter does not pick up system files or read-only files.</span></span> <span data-ttu-id="3a743-140">ディスク上のファイルのみが取得され、デバイス ファイルは取得されません。</span><span class="sxs-lookup"><span data-stu-id="3a743-140">Only disk-based files are picked up, and not device files.</span></span>  

## <a name="using-macros-in-file-names"></a><span data-ttu-id="3a743-141">ファイル名のマクロの使用</span><span class="sxs-lookup"><span data-stu-id="3a743-141">Using macros in file names</span></span>

<span data-ttu-id="3a743-142">一連の定義済みマクロを使用して、ファイル送信ハンドラがメッセージを書き込むファイルを、動的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="3a743-142">You can use a predefined set of macros to dynamically create the files in which the File send handler writes messages.</span></span> <span data-ttu-id="3a743-143">ファイル システム上にファイルを作成する前に、ファイル送信ハンドラによって、ファイル名に含まれるすべてのマクロが個別の値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="3a743-143">Before creating a file on the file system, the File send handler replaces all the macros in the file name with their individual values.</span></span> <span data-ttu-id="3a743-144">1 つのファイル名で複数の異なるマクロを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a743-144">You can use several different macros in one file name.</span></span>  
  
 <span data-ttu-id="3a743-145">ファイル名のマクロは、BizTalk エクスプローラー オブジェクト モデルを使用したファイル送信ハンドラーの構成時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a743-145">You can use the file name macros while configuring the File send handler using the BizTalk Explorer object model.</span></span>  
  
 <span data-ttu-id="3a743-146">次のいずれかの条件に当てはまる場合、ファイル送信ハンドラはマクロを値に置き換えません。</span><span class="sxs-lookup"><span data-stu-id="3a743-146">The File send handler does not replace the macros with a value if any of the following are true:</span></span>  
  
-   <span data-ttu-id="3a743-147">対応するシステム プロパティが設定されていない場合</span><span class="sxs-lookup"><span data-stu-id="3a743-147">The corresponding system property is not set.</span></span>  
  
-   <span data-ttu-id="3a743-148">マクロのスペルが間違っている場合</span><span class="sxs-lookup"><span data-stu-id="3a743-148">The macro is misspelled.</span></span>  
  
-   <span data-ttu-id="3a743-149">マクロの値に、ファイル名には無効な記号が含まれている場合</span><span class="sxs-lookup"><span data-stu-id="3a743-149">The value for the macro contains symbols that are not valid in the file name.</span></span>  
  
 <span data-ttu-id="3a743-150">上記のいずれかの条件に当てはまる場合、ファイル送信ハンドラは、ファイル名に含まれるマクロを変更しません (例、Myfile_%MessageID%.xml)。</span><span class="sxs-lookup"><span data-stu-id="3a743-150">If any of these conditions occur, the File send handler leaves the macros in the file name untouched, for example Myfile_%MessageID%.xml.</span></span>  
  
 <span data-ttu-id="3a743-151">次の表は、サポートされているマクロと、ファイル送信ハンドラによってそのマクロがどのような形式に置換されるのかを示しています。</span><span class="sxs-lookup"><span data-stu-id="3a743-151">The following table lists the supported macros and describes how the File send handler replaces them.</span></span>  
  
|<span data-ttu-id="3a743-152">マクロ名</span><span class="sxs-lookup"><span data-stu-id="3a743-152">Macro name</span></span>|<span data-ttu-id="3a743-153">代入値</span><span class="sxs-lookup"><span data-stu-id="3a743-153">Substitute value</span></span>|  
|----------------|----------------------|  
|<span data-ttu-id="3a743-154">%datetime%</span><span class="sxs-lookup"><span data-stu-id="3a743-154">%datetime%</span></span>|<span data-ttu-id="3a743-155">YYYY-MM-DDThhmmss 形式の協定世界時 (UTC) の日時 (例、1997-07-12T103508)。</span><span class="sxs-lookup"><span data-stu-id="3a743-155">Coordinated Universal Time (UTC) date time in the format YYYY-MM-DDThhmmss (for example, 1997-07-12T103508).</span></span>|  
|<span data-ttu-id="3a743-156">%datetime_bts2000%</span><span class="sxs-lookup"><span data-stu-id="3a743-156">%datetime_bts2000%</span></span>|<span data-ttu-id="3a743-157">YYYYMMDDhhmmsss 形式の UTC 日時。sss は秒およびミリ秒を表します (たとえば、199707121035234 は 1997 年 7 月 12 日 10 時 35 分 23 秒 400 ミリ秒を表します)。</span><span class="sxs-lookup"><span data-stu-id="3a743-157">UTC date time in the format YYYYMMDDhhmmsss, where sss means seconds and milliseconds (for example, 199707121035234 means 1997/07/12, 10:35:23 and 400 milliseconds).</span></span>|  
|<span data-ttu-id="3a743-158">%datetime.tz%</span><span class="sxs-lookup"><span data-stu-id="3a743-158">%datetime.tz%</span></span>|<span data-ttu-id="3a743-159">ローカルの日時に GMT のタイム ゾーンを加えた YYYY-MM-DDThhmmssTZD 形式の日時 (例、1997-07-12T103508+800)。</span><span class="sxs-lookup"><span data-stu-id="3a743-159">Local date time plus time zone from GMT in the format YYYY-MM-DDThhmmssTZD, (for example, 1997-07-12T103508+800).</span></span>|  
|<span data-ttu-id="3a743-160">%DestinationParty%</span><span class="sxs-lookup"><span data-stu-id="3a743-160">%DestinationParty%</span></span>|<span data-ttu-id="3a743-161">送信先パーティの名前。</span><span class="sxs-lookup"><span data-stu-id="3a743-161">Name of the destination party.</span></span> <span data-ttu-id="3a743-162">この値は、メッセージ コンテキスト プロパティ **BTS.DestinationParty**から取得されます。</span><span class="sxs-lookup"><span data-stu-id="3a743-162">The value comes from the message context property **BTS.DestinationParty**.</span></span>|  
|<span data-ttu-id="3a743-163">%DestinationPartyQualifier%</span><span class="sxs-lookup"><span data-stu-id="3a743-163">%DestinationPartyQualifier%</span></span>|<span data-ttu-id="3a743-164">送信先パーティの修飾子。</span><span class="sxs-lookup"><span data-stu-id="3a743-164">Qualifier of the destination party.</span></span> <span data-ttu-id="3a743-165">この値は、メッセージ コンテキスト プロパティ **BTS.DestinationPartyQualifier**から取得されます。</span><span class="sxs-lookup"><span data-stu-id="3a743-165">The value comes from the message context property **BTS.DestinationPartyQualifier**.</span></span>|  
|<span data-ttu-id="3a743-166">%MessageID%</span><span class="sxs-lookup"><span data-stu-id="3a743-166">%MessageID%</span></span>|<span data-ttu-id="3a743-167">BizTalk Server 内のメッセージのグローバル一意識別子 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="3a743-167">Globally unique identifier (GUID) of the message in BizTalk Server.</span></span> <span data-ttu-id="3a743-168">値は、メッセージ コンテキスト プロパティから直接取得**BTS です。MessageID**です。</span><span class="sxs-lookup"><span data-stu-id="3a743-168">The value comes directly from the message context property **BTS.MessageID**.</span></span>|  
|<span data-ttu-id="3a743-169">%SourceFileName%</span><span class="sxs-lookup"><span data-stu-id="3a743-169">%SourceFileName%</span></span>|<span data-ttu-id="3a743-170">ファイル アダプタが読み取るメッセージが存在するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3a743-170">Name of the file from which the File adapter read the message.</span></span> <span data-ttu-id="3a743-171">ファイル名には、拡張子は含まれますが、ファイル パスは含まれません (例、Sample.xml)。</span><span class="sxs-lookup"><span data-stu-id="3a743-171">The file name includes the extension and excludes the file path, for example, Sample.xml.</span></span> <span data-ttu-id="3a743-172">このプロパティを置き換えるときに、ファイル アダプターに格納されている絶対ファイル パスからファイル名を抽出、**ファイル。ReceivedFileName**コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="3a743-172">When substituting this property, the File adapter extracts the file name from the absolute file path stored in the **FILE.ReceivedFileName** context property.</span></span> <span data-ttu-id="3a743-173">コンテキスト プロパティに値がない場合-たとえば、ファイル アダプター以外のアダプタにメッセージを受信しました — マクロ置換しませんし、ファイルの名前をそのままに残ります (C:\Drop など\\%sourcefilename%)。</span><span class="sxs-lookup"><span data-stu-id="3a743-173">If the context property does not have a value—for example, if a message was received on an adapter other than the File adapter—the macro will not be substituted and will remain in the file name as is (for example, C:\Drop\\%SourceFileName%).</span></span> <span data-ttu-id="3a743-174">**注:** このマクロを正しく実装の場合、出力メッセージが受信したメッセージと同じメッセージである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a743-174">**Note:**  Correct implementation of this macro requires that the output message is the same message as the received message.</span></span>|  
|<span data-ttu-id="3a743-175">%SourceParty%</span><span class="sxs-lookup"><span data-stu-id="3a743-175">%SourceParty%</span></span>|<span data-ttu-id="3a743-176">ファイル アダプタが受信したメッセージの受信元パーティの名前。</span><span class="sxs-lookup"><span data-stu-id="3a743-176">Name of the source party from which the File adapter received the message.</span></span> <span data-ttu-id="3a743-177">**注:** このマクロを正しく実装の場合、出力メッセージが受信したメッセージと同じメッセージである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a743-177">**Note:**  Correct implementation of this macro requires that the output message is the same message as the received message.</span></span>|  
|<span data-ttu-id="3a743-178">%SourcePartyQualifier%</span><span class="sxs-lookup"><span data-stu-id="3a743-178">%SourcePartyQualifier%</span></span>|<span data-ttu-id="3a743-179">ファイル アダプタが受信したメッセージの受信元パーティの修飾子。</span><span class="sxs-lookup"><span data-stu-id="3a743-179">Qualifier of the source party from which the File adapter received the message.</span></span> <span data-ttu-id="3a743-180">**注:** このマクロを正しく実装の場合、出力メッセージが受信したメッセージと同じメッセージである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a743-180">**Note:**  Correct implementation of this macro requires that the output message is the same message as the received message.</span></span>|  
|<span data-ttu-id="3a743-181">%time%</span><span class="sxs-lookup"><span data-stu-id="3a743-181">%time%</span></span>|<span data-ttu-id="3a743-182">hhmmss 形式の UTC 時刻。</span><span class="sxs-lookup"><span data-stu-id="3a743-182">UTC time in the format hhmmss.</span></span>|  
|<span data-ttu-id="3a743-183">%time.tz%</span><span class="sxs-lookup"><span data-stu-id="3a743-183">%time.tz%</span></span>|<span data-ttu-id="3a743-184">ローカルの日付に GMT のタイム ゾーンを加えた hhmmssTZD 形式の日付 (例、124525+530)。</span><span class="sxs-lookup"><span data-stu-id="3a743-184">Local time plus time zone from GMT in the format hhmmssTZD (for example, 124525+530).</span></span>|  
  
 
## <a name="receive-folder-and-destination-location-properties-gotchas"></a><span data-ttu-id="3a743-185">フォルダーと移動先の場所のプロパティ潜在的な問題が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a743-185">Receive folder and destination location properties gotchas</span></span>

<span data-ttu-id="3a743-186">ファイルの受信場所は、ファイル受信ハンドラーで読み取るファイルが存在するファイル システムまたはネットワーク共有上のフォルダーのパスを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="3a743-186">The file receive location is a string that contains a path to a folder on a file system or network share from which the File receive handler reads files.</span></span> <span data-ttu-id="3a743-187">ファイルの送信先は、ファイル送信ハンドラーで書き込むファイルが存在するファイル システムまたはネットワーク共有上のフォルダーのパスを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="3a743-187">The file destination location is a string that contains a path to a folder on a file system or network share where the File send handler writes files.</span></span>  
  
 <span data-ttu-id="3a743-188">受信フォルダーおよび送信先のプロパティには、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a743-188">The following restrictions apply to the receive folder and destination location properties:</span></span>  
  
-   <span data-ttu-id="3a743-189">ユーザーのプロパティを指定する場合、その時点でファイル システムまたはネットワーク共有上のファイル パスが存在する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3a743-189">Existence of the file path on a file system or network share is not required at the time when you specify the property in the user.</span></span>  
  
-   <span data-ttu-id="3a743-190">ファイル パスは、絶対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a743-190">The file path must always be absolute.</span></span>  
  
-   <span data-ttu-id="3a743-191">汎用名前付け規則 (UNC) 形式を使用して、ファイルのパスを指定することができます (たとえば、 \\ \\ <*サーバー* \> \\ < *共有*\>)。</span><span class="sxs-lookup"><span data-stu-id="3a743-191">You can specify the file path by using Universal Naming Convention (UNC) format (for example, \\\\<*server*\>\\<*share*\>).</span></span>  
  
-   <span data-ttu-id="3a743-192">サーバー名が、次の文字を含める必要がありますいないファイルのパスが UNC 形式である場合は、: ' ~!</span><span class="sxs-lookup"><span data-stu-id="3a743-192">If the file path is in UNC format, the server name must not contain the following characters: \` ~ !</span></span> <span data-ttu-id="3a743-193">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> / ?</span><span class="sxs-lookup"><span data-stu-id="3a743-193">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> / ?</span></span> <span data-ttu-id="3a743-194">;</span><span class="sxs-lookup"><span data-stu-id="3a743-194">;</span></span>  
  
-   <span data-ttu-id="3a743-195">親を使用することはできません (\\..\\) と現在 (\\.\\) ファイルのパスの任意の部分でフォルダー記号。</span><span class="sxs-lookup"><span data-stu-id="3a743-195">You cannot use parent (\\..\\) and current (\\.\\) folder symbols in any part of the file path.</span></span>  
  
-   <span data-ttu-id="3a743-196">ファイル パスでは、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="3a743-196">The file path is not case-sensitive.</span></span>  
  
-   <span data-ttu-id="3a743-197">ファイルのパスには、次の文字を含めることはできません: \< \> :/&#124;です。" ?</span><span class="sxs-lookup"><span data-stu-id="3a743-197">The file path cannot contain any of the following characters: \< \> : / &#124; " ?</span></span> <span data-ttu-id="3a743-198">\* ;</span><span class="sxs-lookup"><span data-stu-id="3a743-198">\* ;</span></span>  
  
-   <span data-ttu-id="3a743-199">予約されたデバイス名 (CON、PRN、AUX、CLOCK$、NUL、COM1、COM2、COM3、COM4、COM5、COM6、COM7、COM8、COM9、LPT1、LPT2、LPT3、LPT4、LPT5、LPT6、LPT7、LPT8、および LPT9) は、ファイル パスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3a743-199">You cannot use the following reserved device names in the file path: CON, PRN, AUX, CLOCK$, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, and LPT9.</span></span>  
  
-   <span data-ttu-id="3a743-200">ファイル パス、ファイル マスク、またはファイル名の長さの合計 (マクロでの代入を除く) は 256 文字以下にしてください</span><span class="sxs-lookup"><span data-stu-id="3a743-200">Total length of file path, file mask, or file name (without macro substitution) must not exceed 256 characters.</span></span> <span data-ttu-id="3a743-201">(これはメッセージ ボックス データベースの制限です)。</span><span class="sxs-lookup"><span data-stu-id="3a743-201">(The MessageBox database imposes this restriction.)</span></span>  
  
-   <span data-ttu-id="3a743-202">ファイル アダプターがファイルのパスの Unicode 仕様をサポートしていない (たとえば、"\\\\?\\") です。</span><span class="sxs-lookup"><span data-stu-id="3a743-202">The File adapter does not support Unicode specification of the file path (for example, "\\\\?\\").</span></span>  
  
 <span data-ttu-id="3a743-203">受信フォルダーのプロパティのみに、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a743-203">Restrictions on the receive folder property only:</span></span>  
  
-   <span data-ttu-id="3a743-204">シンボリック リンクを使用して、Microsoft Windows NT の分散ファイル システムを使用するフォルダーには、受信フォルダーのプロパティを設定しません。</span><span class="sxs-lookup"><span data-stu-id="3a743-204">Do not set the receive folder property to a folder that uses the Microsoft Windows NT Distributed File System with a symbolic link.</span></span> <span data-ttu-id="3a743-205">Windows NT の分散ファイル システムを使用している場合は、直接的なファイル アダプターのネットワーク パスのフォルダーを使用する受信場所のみをできます。</span><span class="sxs-lookup"><span data-stu-id="3a743-205">If you are using Windows NT Distributed File System, you can only use folders with straight network paths in File adapter receive locations.</span></span>  
  
-   <span data-ttu-id="3a743-206">ドキュメントが UNC パスに送信され、ファイル アダプターの受信場所でサーバーが受信するドキュメントが複数ある場合、その UNC パスに送信されたドキュメントの大半は、1 台のサーバーのみで取得および処理されます。</span><span class="sxs-lookup"><span data-stu-id="3a743-206">When documents are sent to a UNC path, and you have more than one server receiving documents at the receive location for the File adapter, only one server will pick up and process most of the documents sent to that UNC path.</span></span> <span data-ttu-id="3a743-207">ファイル名の変更の詳細についてを参照してください、ファイル受信アダプターの[ファイル アダプター](../core/file-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="3a743-207">For more information about file renaming, see the File Receive Adapter section of [File Adapter](../core/file-adapter.md).</span></span>  
  
 <span data-ttu-id="3a743-208">送信フォルダーのプロパティのみに、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a743-208">Restrictions on the send folder property only:</span></span>  
  
-   <span data-ttu-id="3a743-209">Microsoft Windows Vista など、サーバーでないオペレーティング システムでファイル アダプターを実行している場合、すべてのメッセージを同時にバッチ処理するために必要なオペレーティング システム リソースが不足する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a743-209">The file adapter may not have enough operating system resources to process all of the messages in a batch concurrently when running on a non-server operating system like Microsoft Windows Vista.</span></span>  
  
 <span data-ttu-id="3a743-210">ファイル アダプターでは、上記のルールを使用して、デザイン時にファイル パスを検証します。</span><span class="sxs-lookup"><span data-stu-id="3a743-210">The File adapter validates the file path at design time by using the previously mentioned rules.</span></span> <span data-ttu-id="3a743-211">さらに、ファイル アダプターを使用する動的ポート経由でメッセージを送信する場合、実行時にメッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="3a743-211">In addition, the File adapter validates the message at run time if the adapter sends the message through a dynamic port with a File adapter.</span></span>  
  
